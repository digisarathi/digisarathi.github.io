---
layout: default
title: Insights
permalink: /insights/
---

<div class="home">

{%- if site.posts.size > 0 -%}
    <h2 class="post-list-heading">{{ page.list_title | default: "Insights" }}</h2>
    <ul class="post-list">
      {%- for post in site.posts -%}
      <li >
        <h3 >
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <span class="post-meta"   >{{ post.date | date: date_format }}</span>
        {% if post.content contains site.excerpt_separator %}
          {{ post.excerpt }}
        {%- endif -%}
        <div style="margin-bottom:1.5em;"></div>
      </li>
      {%- endfor -%}
    </ul>

    <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
{%- endif -%}
</div>