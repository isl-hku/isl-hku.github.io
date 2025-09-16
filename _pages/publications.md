---
title: "Publications"
layout: gridlay
excerpt: "Publications."
sitemap: true
permalink: /publications/
description:
nav: true
toc: true
---

<!-- Navigation Tabs -->
<ul class="nav nav-tabs" style="width:100%; margin: 0 auto;">
<li class="active">
<a data-toggle="tab"><button id="btn_bytype" onclick="ShowOrHide('bytype')">By Type</button></a>
</li>
<li class="">
<a data-toggle="tab"><button id="btn_byyear" onclick="ShowOrHide('byyear')">By Year</button></a>
</li>
</ul>

<br>

{% assign this_year = "now" | date: "%Y" %}
{% assign years = (1998..this_year) | reverse %}

<script>var byyeartext = "year"; var bytypetext = "type";</script>

<!-- Display by Year -->
<div id="byyear" style="display:none;">
{% for y in years %}
<h3 id="{{ y }}">{{ y }}</h3>
{% bibliography -f journal -f conf -q @*[year={{ y }}]* %}
{% endfor %}
</div>

<!-- Patents -->
<div id="bypatent" style="display:none;">
{% bibliography -f others -q @patent %}
</div>


<!-- Display by Type (Default) -->
<div id="bytype" style="display:block;">
## Journal papers
{% bibliography -f journal -q @article[key!=Liu2025JOpt && key!=CPChen2023OE] %}

## Conference
{% bibliography -f conf -q @inproceedings %}

## Editorials
{% bibliography -f others -q @editorial %}
</div>

<br>
<br>