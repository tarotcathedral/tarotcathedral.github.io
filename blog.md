---
layout: page
title: Blog
permalink: /blog/
---

<h2>Blog – Tarot Cathedral</h2>

<p>
  Wszystkie artykuły dotyczące Tarot de Marseille, symboliki kart, historii i numerologii.
</p>

<hr style="margin: 40px 0;">

<!-- Lista wszystkich wpisów -->
{% for post in site.posts %}
  <article style="margin-bottom: 50px;">
    <h3>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h3>
    
    <p style="color: #666; font-size: 0.95rem;">
      {{ post.date | date: "%d %B %Y" }}
      {% if post.tags.size > 0 %}
        • 
        {% for tag in post.tags %}
          <span style="background: #f0e6d9; padding: 2px 8px; border-radius: 4px; font-size: 0.85rem;">#{{ tag }}</span>
        {% endfor %}
      {% endif %}
    </p>

    {% if post.excerpt %}
      <p>{{ post.excerpt | strip_html | truncate: 280 }}</p>
    {% endif %}

    <p><a href="{{ post.url }}" style="color: #8B3A1E; font-weight: 500;">Czytaj dalej →</a></p>
  </article>
{% endfor %}

{% if site.posts.size == 0 %}
  <p style="font-style: italic; color: #777;">
    Jeszcze nie ma żadnych artykułów. Pierwszy pojawi się wkrótce!
  </p>
{% endif %}
