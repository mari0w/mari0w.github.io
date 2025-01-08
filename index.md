---
layout: default
---

{% for post in site.posts | sort: 'date' | reverse limit: 10 %}
- [{{ post.title }}]({{ post.url }}) {{post.date}}
{% endfor %}

---

{% assign all_categories = site.posts | map: 'categories' | flatten | uniq | compact %}
{% for category in all_categories %}
- [{{ category }} ({{ site.posts | where_exp: "post", "post.categories contains category" | size }})](/categories/{{ category | slugify }})
{% endfor %}



