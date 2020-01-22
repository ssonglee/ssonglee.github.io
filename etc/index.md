---
layout: default
title: "etc"
description: 끄적끄적
main: true
etc: true
project-header: true
---

<ul class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.etc == true %}
    {% include post-list.html %}
{% endif %}
{% endfor %}
</ul>