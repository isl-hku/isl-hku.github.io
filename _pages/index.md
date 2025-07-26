---
title: "ISL"
layout: gridlay
excerpt: "AISI"
sitemap: false
permalink: /
---




<br>

Imaging Systems Laboratory at the University of Hong Kong, led by Prof. Edmund Y. Lam, is dedicated to advanced research in computational imaging, combining aspects of electronic engineering, computer vision, and optical engineering. Its primary interests lie in the development of novel algorithms for unconventional imaging systems and leveraging AI in imaging applications. The lab offers various opportunities, including roles for Post-doctoral Fellows, Principal/Senior Researchers, and Graduate Students, catering to individuals with a strong academic background and a passion for innovative research in imaging technologies.



<div class="container content post">
  <h2>
    <center>
    <!-- <strong>{{ page.title }}</strong><br/>
    <small>{{ page.date | date: '%B %-d, %Y'}} | </small>
    <small>{{ site.first_name}} {{ site.last_name}}</small> -->
    </center>
  </h2> 
<hr> 



<img src="{% if post.header-img %}{{ site.baseurl }}/assets/images/post/{{ page.header-img }}{% else %}  {% endif %}" style="width:40%; float: right; margin-left: 10px;">

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
<img src="{% if post.header-img %}{{ site.baseurl }}/assets/images/post/{{ post.header-img }}{% else %}  {% endif %}" style="width:45%; float: right; margin-left: 10px; margin-top:10px;">
<p class="list-detail">
  {% if post.lang == "zh" %}
    {{ post.content | strip_html | truncate: 500 }}
  {% else %}
    {{ post.content | strip_html | truncatewords: 100 }}
  {% endif %}
</p>
<!-- </div> -->
</div>
</div>
<hr>
{% endfor %}
</div>


<hr>
 


<style>
.post img, .content img {
  max-width: 100% !important;
  height: auto !important;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
@media (max-width: 768px) {
  .post img, .content img {
    max-width: 98vw !important;
    width: 100% !important;
    height: auto !important;
  }
  .post table, .content table {
    display: block;
    width: 100%;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
  }
}
.post {
  position: relative;
  margin-right: 320px;
}


@media (max-width: 1100px) {
  .post {
    margin-right: 220px;
  }
  .post ul.toc {
    width: 200px;
  }
}

@media (max-width: 900px) {
  .post {
    margin-right: 0;
  }
  .post ul.toc {
    position: static;
    float: none;
    width: 100%;
    max-width: 100%;
    margin: 1em 0;
    top: auto;
    z-index: auto;
    max-height: none;
    overflow: visible;
  }
}
</style>

  
</div>
