---
layout: page
---

{{ site.description }}

<!-- <h1>Archive of posts with {{ page.type }} '{{ page.title }}'</h1> -->
<ul class="posts">
  {% for post in site.posts limit:5 %}
    <li>
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>

<!-- <p>{{ posts.excerpt }}</p> -->

<a href="/archive.html">more...</a>
