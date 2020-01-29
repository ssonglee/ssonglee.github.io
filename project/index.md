---
layout: default
work: true
main: true
title: "Projects"
description: 경험했던 프로젝트
project-header: true
header-img: "img/project_bg.jpg"
---

<div class="catalogue">
{% assign sorted = site.pages | reverse %}
{% for page in sorted %}
{% if page.projects == true %}

     {% include post-list.html %}

{% endif %}
{% endfor %}
</div>