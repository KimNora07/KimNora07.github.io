---
title: "Game" # 카테고리 이름
layout: archive
permalink: /categories/Game/
author_profile: true
types: posts
---

{% assign posts = site.categories['Game']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}