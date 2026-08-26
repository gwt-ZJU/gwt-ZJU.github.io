---
layout: page
title: 项目 @ projects
permalink: /projects/
description: <span class="lang-zh">科研项目与工作展示</span><span class="lang-en">Research projects and work</span>
nav: true
nav_order: 3
display_categories: [科研项目, 其他]
horizontal: false
---

<!-- pages/projects.md -->

<span class="lang-zh">以下展示我主持或参与的研究项目与平台，点击卡片查看项目详情。</span><span class="lang-en">Below are research projects and platforms I lead or participate in. Click a card for details.</span>

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{%- if category == "科研项目" -%}<span class="lang-zh">科研项目</span><span class="lang-en">Research Projects</span>{%- elsif category == "其他" -%}<span class="lang-zh">其他</span><span class="lang-en">Others</span>{%- else -%}{{ category }}{%- endif -%}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
