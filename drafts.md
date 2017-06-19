---
layout: post
title: Draft Blog Posts
---
{% if site.tags.draft.size != 0 %}
	{% for post in site.tags.draft %}

## [{{ post.title }} ]({{ post.url }})
{{ post.date | date_to_string }}
  {{ post.excerpt }}
[read more]({{ post.url }})

	{% endfor %}
{% endif %}

