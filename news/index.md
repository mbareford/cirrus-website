---
layout: section
title: News &amp; Announcements
summary: All the latest updates and information from the Cirrus service.
banner: web_banners_02.jpg
---



{% for post in site.posts %}
<div class="post-area">
  <a href="{{ post.url | prepend: site.baseurl }}" class="bold">{{ post.title }}</a>
  <p class="post-date">{{ post.date | date_to_long_string }}

  &nbsp;&nbsp;&nbsp;&nbsp;
  {{ post.author }}

      &nbsp;&nbsp;&nbsp;&nbsp;
      {% for tag in post.tags %}
        {% capture tag_name %}{{ tag }}{% endcapture %}
        <a href="/about/news/{{ tag_name }}" ><code  style="font-size:15px;"><nobr>{{ tag_name }}</nobr></code>&nbsp;</a>
      {% endfor %}         
  </p>

  <p>
    {{ post.content | strip_html | truncatewords: 50 }}
  </p>
</div>
{% endfor %}




