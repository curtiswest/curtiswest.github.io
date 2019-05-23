---
layout: post
title:  "Virtual Reality Project"
date:   2016-10-24
image: https://i.imgur.com/T5Ffpsh.png
excerpt: "Lessons learned during the year-long management of a mobile VR app's development."
tag:
- project management
- portfolio
comments: true
---

Griffith University software engineering students undertake a year-long project with an industry partner for exposure to a real-world project with a real-world client. As project manager (and 3D modeler - but that's a post for another time), I was tasked with documenting and managing the overall progress of the project, including ensuring that team members were capitalising on our diverse skill-sets to deliver maximum (and timely) results. Along the way, I learned several valuable lessons, implemented solutions to assist the team and developed skills in managing and communicating with my team.

## Project Context
Griffith University is keen on the exploration and application of emerging technology in the academic field. So much so, in fact, that GU has a laboratory dedicated to just that: [Innovative Design and Emerging Technology Lab (IDEA Lab)](http://www.ict.griffith.edu.au/idea/). IDEA Lab works in a range of fields, particularly virtual and augmented reality technology.

Our project fell under the IDEA Lab for guidance, supervision and ultimately project assessment. Our 4-person team was given a two-part project brief: explore the use of cheap mobile VR headsets for a client in the tourism market, and develop it inside/alongside a portal that can be used to demonstrate future GU VR apps. We were given freedom in the software development lifecycle methodology that we employed and therefore in the way we undertook the project - but 'strict' documentation was still required in a certain format for grading purposes.

## Finding Our Feet
In the scheme of mobile VR, no platform is really more established than [Google Cardboard](https://vr.google.com/cardboard/). This was our first port of call, as it offers widely-available, <$20 cardboard VR headsets compatible with most modern smartphone and has an ecosystem of apps already built with it.

We knew essentially very little going into the project; none of us had ever developed for VR before, let alone developed full-fledged *mobile* apps, so we knew from the very beginning that we would need to embrace changes to succeed.

We knew that each of us had different and specialised skill-sets, and that we needed the freedom to work on tasks that best suited those skill-sets. I quickly recognised that micromanaging or delegating tasks was certainly no way to go about having a happy and functioning team, so I knew that moving forward we'd have to find a way to each choose our own tasks but still contribute to the overall project progress.

We knew that we had documentation standards to adhere to (grading requirements, remember?) and that whatever we did, we would need a way to document it to the standard.

Given all the above, we established that we would adhere to the [Scrum framework](https://en.wikipedia.org/wiki/Scrum_(software_development)) (an iterative and incremental Agile-based SDLC) as closely addresses the above.

## Requirements
Going into the project, we had only our project brief. We worked closely with our industry client to discover their ideal end-product. For context, our client is a well-known tourism operator on the Great Barrier Reef. We worked extensively with them to through an iterative process to establish several key requirements that the app would have:
* Show the beauty of the reef and entice potential tourists to visit
* Tactfully discuss the issue of the reef's health, further to the next point
* Establish a vested interest in users so that they would respect and care for the reef more than just a 'day out on a boat'

From this, we generated a product backlog of user stories representing the product owner's best understanding of the project. This all went into a [Trello](https://trello.com/) board, which worked well for overall progress tracking, but we quickly outgrow what Trello could provide for a fast-moving software development team (no hate to the team at Trello, it's not you, it's me).

## Lessons learned
* **Automating the boring stuff is vital for team morale and productivity.** I implemented an automated reporting and time-tracking solution that removed the need for a team member to manually update these reports weekly (for university assessment purposes). With that out of the way, everyone could focus on properly productive work and not the menial stuff. 
* **Spending time to evaluate and customise tools is repaid ten-fold, if done properly.** We started out working with Trello, but moved to a full-fledged Atlassian-based system with JIRA, BitBucket, etc. which integrated with the above automation much easier.
* **Regular contact is vital in a distributed-team scenario**. While the status of the project could be seen from our JIRA sprint backlog, really, there is no substitute for a face-to-face meeting. A JIRA issue doesn't tell you how stressed or busy a person is. 
* **Client feedback early and client feedback often**. Some of our early work was basically discarded because we didn't involve the client enough. Towards the end, we had regular feedback meetings with our clients and the quality of our work (and quantity of rework) reflected this. 