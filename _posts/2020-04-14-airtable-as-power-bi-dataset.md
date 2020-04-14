---
layout: post
title:  "How to use Airtable as a Power BI data source"
date:   2020-04-14
excerpt: "A solution to extract data from Airtable tables that is compatible with scheduled refresh."
image: /assets/images/pbi_blank_query.png
tag:
- portfolio
- powerbi
- howto
comments: true
---

[Airtable](https://airtable.com) is a unique solution -- something I describe as a hybrid between an Excel spreadsheet and a fully-fledged database. It's combination of flexibility and control lends itself well to developing tooling for clients that don't have the appetite for a scratch-built solution. 

Airtable doesn't (yet) have a native connector for Power BI. However, Airtable provides a very well-structured API that allows for accessing this through the Power Query service. The complexity in this connector is that Airtable's API responds with pages of data. Others on the net have provided solutions to the pagination problem, but most of the solutions I've seen are not compatible with scheduled refresh.

This solution allows you to schedule refresh while using Airtable as a data source. 

## Airtable API keys and IDs

Given we're using the Airtable API, you'll need a few keys to authenticate and access data. Visit the relevant Base and click `Help` > `API documentation` in the top-right hand side -- this cleverly self-updates to reflect your base's structure (nice work, Airtable!)

3 quick steps:
1. Record the `Base ID`. This looks like `app<SomeRandomLettersAndNumbers>` and appears at the top of the page.
2. Record the relevant `Table name`, e.g. `My Table`. You don't need to encode spaces.
3. Record your `API key` accessible from [your Airtable account page](https://airtable.com/account).


## Power BI query
In Power BI, create a new `blank query` data source.

![Create a new Power BI blank query](/assets/images/pbi_blank_query.png "Create a new Power BI blank query")

Open the `Advanced Editor`.

![Open the advanced editor](/assets/images/pbi_advanced_editor.png "Open the advanced editor")

Paste the below code in. You'll need to replace the following variables in `BaseURL` (make sure to remove the <> symbols too): `BASE_ID`, `TABLE_NAME`, `API_KEY`, 
```
let
	BaseURL = "https://api.airtable.com/v0/<BASE_ID>/<TABLE_NAME>?api_key=<API_KEY>",
	Pagination = List.Skip(List.Generate( () => [Last_Key = "init", Counter=0],
   		each  [Last_Key] <> null,
   		each [ Last_Key = try if [Counter]<1 then "" else [WebCall][Value][offset] otherwise null,
                       WebCall = try if [Counter]<1 then Json.Document(Web.Contents(BaseURL)) 
                       else Json.Document(Web.Contents(BaseURL, [Query=[offset=Last_Key]])),
    		       Counter = [Counter]+1
                      ],
   		each [WebCall]
    ),1),
    #"Converted to Table" = Table.FromList(Pagination, Splitter.SplitByNothing(), null, null, ExtraValues.Error),
    #"Expanded Column1" = Table.ExpandRecordColumn(#"Converted to Table", "Column1", {"HasError", "Value"}, {"HasError", "Value"}),
    #"Expanded Value" = Table.ExpandRecordColumn(#"Expanded Column1", "Value", {"records"}, {"Value.records"}),
    #"Expanded Value.records" = Table.ExpandListColumn(#"Expanded Value", "Value.records"),
    #"Expanded Value.records1" = Table.ExpandRecordColumn(#"Expanded Value.records", "Value.records", {"id", "fields", "createdTime"}, {"Value.records.id", "Value.records.fields", "Value.records.createdTime"})
in
    #"Expanded Value.records1"
```

That's it! You'll be presented with a table of records, of which you can expand as drill down into as necessary (the pink arrow in the below photo). Repeat this to add as many Airtable bases as data source as you require.

![Airtable data imported into in Power BI](/assets/images/pbi_airtable_results.png "Airtable data imported into in Power BI")

Hopefully this helps anyone else using the powerful combination of Airtable and Power BI. Feel free to reach out on the below contact details if you have a question or would like a hand!