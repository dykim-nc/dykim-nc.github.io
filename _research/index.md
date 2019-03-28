---
layout: collection
title: Research
categories: []
permalink: /:collection/index.html
index: true
---
{% assign collection = site.collections | where:"label", page.collection | first %}
{{ collection.description }}

### Posts
{% assign sorted = collection.docs | where:"layout", "post" | sort: 'date' %}
{% for item in sorted %}
* [{{ item.title }}]({{ item.url }})
> {{ item.excerpt }}
{% endfor %}