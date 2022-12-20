---
layout: archive
permalink: /projects/
title: "Research projects"
author_profile: true
---

{% include base_path %}

{% for projects in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
