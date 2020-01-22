---
layout: default
work: true
main: true
title: "etc"
description: 끄적끄적...
project-header: true
---

<div class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.etc == true %}

     {% include post-list.html %}

{% endif %}
{% endfor %}
</div>