---
layout: archive
permalink: /posts/
title: "Blog posts"
author_profile: true
#header:
  #og_image: "posts/spatial-sql/gadm_wkt_filter_buffer-1.png"
---

<!--- Coming soon!

<img src="{{ "/images/staytuned.gif" | prepend: site.baseurl | prepend: site.url}}" alt="coming soon" /> --->

 
{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% include archive-single.html %}
{% endfor %}
