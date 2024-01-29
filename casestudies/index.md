---
layout: section
title: Case Studies
summary: Highlights from some of the research carried out on Cirrus
banner: web_banners_02.jpg
---



{% for casestudies in site.casestudies reversed %}
<div class="post-area">
  <a href="{{ casestudies.url | prepend: site.baseurl }}" class="bold">{{ casestudies.title }}</a>
  <p class="post-date">{{ casestudies.date | date_to_long_string }}

  &nbsp;&nbsp;&nbsp;&nbsp;
  {{ casestudies.author }}

<!--
      &nbsp;&nbsp;&nbsp;&nbsp;
      {% for tag in post.tags %}
        {% capture tag_name %}{{ tag }}{% endcapture %}
        <a href="/about/news/{{ tag_name }}" ><code  style="font-size:15px;"><nobr>{{ tag_name }}</nobr></code>&nbsp;</a>
      {% endfor %}   
-->
      
  </p>

  <p>
    {{ casestudies.content | strip_html | truncatewords: 50 }}
  </p>
</div>
{% endfor %}




