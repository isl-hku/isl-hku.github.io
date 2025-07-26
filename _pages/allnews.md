---
title: "News"
layout: textlay
excerpt: ""
sitemap: false
permalink: /allnews.html
tweets:
  - https://twitter.com/ni_chen/status/1727093047190839388
a_tweet: https://twitter.com/ni_chen/status/1710761215256092930
---

# News

<br>

<hr>

{% for article in site.data.news %}

<p style="font-weight:bold">{{ article.date }} : <em >{{ article.headline }}</em>
</p>
<p>
<a href="{{article.link}}">
<img style="height:1000px; float: right; margin-left:15px; margin-bottom:0px; margin-right:0px; margin-top:-15px;" src="{{ site.url }}{{site.baseurl}}/assets/images/news/{{article.avatar}}" data-action="zoom"></a>
 {{ article.summary }}
</p>
<hr>
<br>
{% endfor %}

<!-- <center>
<a class="twitter-timeline" data-lang="en" data-width="500" data-dnt="true" href="https://twitter.com/ni_chen?ref_src=twsrc%5Etfw"></a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</center> -->


