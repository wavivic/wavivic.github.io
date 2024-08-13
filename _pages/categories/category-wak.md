---
title: "Wak"
layout: category
permalink: /categories/wak
author_profile: true
taxonomy: Wak
sidebar:
  nav: "categories"
---
{% assign posts = site.categories['wak']%}
{% for post in posts %}
{% include archive-single.html type=page.entries_layout %}
{% endfor %}