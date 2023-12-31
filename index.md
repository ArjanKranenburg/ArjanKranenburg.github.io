---
layout: page
---

{{ site.description }}

<ul class="posts">
  {% for post in site.posts limit:5 %}
    <li class="index">
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {{ post.excerpt }}
      <a class="read-more" href="{{ post.url | relative_url }}">Read more...</a>
    </li>
  {% endfor %}
</ul>

<a href="/archive.html">more...</a>
