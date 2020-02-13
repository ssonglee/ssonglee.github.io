---
layout: default
work: true
main: true
title: "etc"
description: 알아두면 피가되고 살이되는
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