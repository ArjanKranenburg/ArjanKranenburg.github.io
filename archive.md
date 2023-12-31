---
layout: page
title: Blog Archive
---

  <ul>
    {% for post in site.posts %}
      <li>
        <a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a>
        {% for tag in post.tags %}
          {% if tag != "other" %}
            <div class="pill">{{ tag }}</div>
          {% endif %}
        {% endfor %}
      </li>
    {% endfor %}
  </ul>

<!-- {% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %} -->