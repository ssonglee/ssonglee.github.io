---
layout: default
work: true
main: true
title: "Projects"
description: 경험했던 프로젝트
project-header: true
header-img: "img/project_bg.jpg"
---

<ul class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
  {% for page in sorted %}
  {% if page.projects == true %}
    {% include post-list.html %}
  {% endif %}
{% endfor %}
</ul>
{% if paginator.total_pages > 1 %}
  <div class="pagination">
    {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url | replace: '//', '/' }}" class="button" >
      <i class="fa fa-chevron-left"></i>
      {{ site.theme_settings.str_previous_page }}
    </a>
    {% endif %}
    {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url | replace: '//', '/' }}" class="button" >
      {{ site.theme_settings.str_next_page }}
      <i class="fa fa-chevron-right"></i>
    </a>
    {% endif %}
  </div>
  {% endif %}
