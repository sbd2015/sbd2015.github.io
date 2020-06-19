---
layout: page
permalink: /daily/
title: "Daily"
tags: [blog, graphic design]
image:
  feature: hamburg.jpg
---

<article class="archive-wrap">
  <ol class="post-list">
    {% for post in site.posts %}
      {% if post.category contains "daily" %}
        <li>
          <div
            class="deets"
            itemscope
            itemtype="http://schema.org/BlogPosting"
            itemprop="blogPost"
          >
            <h1><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></h1>
            <p class="date">
              <time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">
                {{ post.date | date: "%B %d, %Y" }}
              </time>
            </p>
            <p class="">
              {% if post.description %}
                {{ post.description | strip_html | strip_newlines | truncate: 120 }}
              {% else %}
                {{ post.content | strip_html | strip_newlines | truncate: 120 }}
              {% endif %}
            </p>
          </div>
        </li>
        {% endif %} 
    {% endfor %}
  </ol>
</article>
