---
title: "Posts"
layout: gridlay
permalink: /posts/
excerpt: "posts."
title: "Posts"
description:
nav: true
toc: true
---


<div class="content list">
{% for post in site.posts %}
<div class="list-item">
<div class="row" style="margin-bottom: 0px; padding-bottom:0px;">
<!-- <div class="col-sm-4">
<img src="{% if post.header-img %}{{ site.baseurl }}/assets/images/post/{{ post.header-img }}{% else %} {{ site.baseurl }}/assets/images/post/dummy.png {% endif %}" style="width:100%;">
</div> -->

<!-- <div class="col-sm-8"> -->
<h3 class="post-title"><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
<p class="list-post-title"> {{ post.date | date: "%B %-d, %Y" }}</p>
<img src="{% if post.header-img %}{{ site.baseurl }}/assets/images/post/{{ post.header-img }}{% else %}  {% endif %}" style="width:30%; float: right; margin-left: 10px; margin-top:10px;">
<p class="list-detail">
  {% if post.lang == "zh" %}
    {{ post.content | strip_html | truncate: 500 }}
  {% else %}
    {{ post.content | strip_html | truncatewords: 120 }}
  {% endif %}
</p>
<!-- </div> -->
</div>
</div>
<hr>
{% endfor %}
</div>
