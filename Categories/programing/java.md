---
layout: page
title: Java
permalink: /Categories/programing/java
---

{% include taxonmomies.html %}

<hr/>

<div class="home">

  {% if site.paginate %}
  {% assign posts = paginator.posts %}
  {% else %}
  {% assign posts = site.posts %}
  {% endif %}

  {%- if posts.size > 0 -%}
  <ul class="post-list">
    {%- assign date_format = site.date_format | default: "%b %-d, %Y" -%}
    {%- for post in posts -%}
    {%- if post.catagories contains "java" or post.catagories contains "Java" or post.catagories contains "JAVA" -%}
    <li>
      <h2>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h2>
      <span class="post-meta">{{ post.date | date: date_format }}</span>
      {%- if post.show_excerpts != false -%}
      <div class="post-excerpt">{{ post.excerpt }}</div>
      {%- endif -%}
    </li>
    {%- endif -%}
    {%- endfor -%}
  </ul>
  

  {% if site.paginate %}
  <div class="pager">
    <ul class="pagination">
      {%- if paginator.previous_page %}
      <li><a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page">{{ paginator.previous_page
          }}</a></li>
      {%- else %}
      <li>
        <div class="pager-edge">•</div>
      </li>
      {%- endif %}
      <li>
        <div class="current-page">{{ paginator.page }}</div>
      </li>
      {%- if paginator.next_page %}
      <li><a href="{{ paginator.next_page_path | relative_url }}" class="next-page">{{ paginator.next_page }}</a></li>
      {%- else %}
      <li>
        <div class="pager-edge">•</div>
      </li>
      {%- endif %}
    </ul>
  </div>
  {%- endif %}

  {%- endif -%}

</div>