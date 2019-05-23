---
title: Portfolio
layout: landing
excerpt: "A small collection of projects that I've worked on."
nav-menu: true
show_tile: true
tile_weight: 10
---

<!-- Main -->
<div id="main">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h2>What you'll find here</h2>
		</header>
		<p>Here are some posts about work I've done in the past. By no means is it exhaustive (then this would take longer than the projects itself!) but hopefully they give you a good sense of what I'm up to.</p>
	</div>
</section>

<!-- Two -->
<section id="two" class="spotlights">
	{% for post in site.posts %}
       	{% if post.title != 404 and post.tag contains 'portfolio' %}
		<section>
			{% if post.image %}
			<a href="generic.html" class="image">
				<img src="{{ post.image }}" alt="" data-position="center center" />
				}
			</a>
			{% endif %}
			<div class="content">
				<div class="inner">
					<header class="major">
						<h3>{{ post.title }}</h3>
					</header>
					<p>{{ post.excerpt }}</p>
					<ul class="actions">
						<li><a href="{{ post.url | relative_url }}" class="button">Learn more</a></li>
					</ul>
				</div>
			</div>
		</section>
		{% endif %}
	{% endfor %}
</section>
</div>
