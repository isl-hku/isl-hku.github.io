---
title: "News"
layout: textlay
excerpt: ""
sitemap: false
permalink: /allnews.html
---

# News

<style>
/* Scoped to All News page */
.news-list { list-style: none; padding-left: 0; }
.news-entry { overflow: auto; }
.news-image-right {
	float: right;
	width: 30%;
	height: auto;
	margin-left: 12px;
	margin-bottom: 6px;
  margin-top: -35px;
}
@media (max-width: 767px) {
	.news-image-right { float: none; width: 100%; margin: 8px 0 10px 0; }
}
</style>


{% assign sorted_news = site.data.news | where: 'tweet', nil | where: 'linkedin', nil | sort: 'date' | reverse %}


{% assign current_year = nil %}
<ul class="news-list">
{% for article in sorted_news %}
{% assign year = article.date | slice: 0, 4 %}
{% if year != current_year %}
{% assign current_year = year %}
<li class="news-year-divider"><h3 class="news-year" id="y{{ current_year }}">{{ current_year }}</h3></li>
{% endif %}
<li class="news-entry">
<div class="news-meta text-sm"><time datetime="{{ article.date | date: '%Y-%m-%d' }}">{{ article.date }}</time></div>
{% if article.headline %}
<h4 class="news-title" >
{% if article.link %}
<a href="{{ article.link }}" target="_blank" rel="noopener">{{ article.headline }}</a>
{% else %}
{{ article.headline }}
{% endif %}
</h4>
{% endif %}
<div class="news-body">
{% if article.avatar %}
	{% if article.link and article.link != '' %}
		<a href="{{ article.link }}">
			<img class="news-image-right" src="{{ site.url }}{{site.baseurl}}/assets/images/news/{{ article.avatar }}" alt="{{ article.headline | strip_html }}" loading="lazy" data-action="zoom">
		</a>
	{% else %}
		<img class="news-image-right" src="{{ site.url }}{{site.baseurl}}/assets/images/news/{{ article.avatar }}" alt="{{ article.headline | strip_html }}" loading="lazy" data-action="zoom">
	{% endif %}
{% endif %}
{% if article.summary and article.summary != '' %}
{{ article.summary }}
{% elsif article.link %}
{{ article.link | fetch_summary: 500 }}
{% endif %}
</div>
</li>
{% endfor %}
</ul>

