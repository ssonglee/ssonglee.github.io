---
layout: default
title: "Study"
description: 공부 한 것을 기록해요.
main: true
project-header: true
header-img: img/about.jpg
---

<ul class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.study == true %}
{% include post-list.html %}
{% endif %}
{% endfor %}
</ul>