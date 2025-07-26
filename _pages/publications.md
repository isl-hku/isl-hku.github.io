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
<li class="">
<a data-toggle="tab"><button id="btn_bybook" onclick="ShowOrHide('bybook')">Book / Book Chapters</button></a>
</li>
<li class="">
<a data-toggle="tab"><button id="btn_bypatent" onclick="ShowOrHide('bypatent')">Patents</button></a>
</li>
<li class="">
<a data-toggle="tab"><button id="btn_bygroup" onclick="ShowOrHide('bygroup')">By Key Words</button></a>
</li>
<li class="">
<a data-toggle="tab"><button id="btn_inpress" onclick="ShowOrHide('inpress')">Preprint</button></a>
</li>
</ul>

<br>

{% assign this_year = "now" | date: "%Y" %}
{% assign years = (1999..this_year) | reverse %}

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

<!-- Display by Key Words (with in-page links) -->
<div id="bygroup" style="display:none;">
<strong>All keywords:</strong> \| 
{% assign all_groups = "AI and deep learning, biomedical microscopy, compressed sensing, computational imaging, computational lithography, digital holography, education technology, electronic imaging, eye imaging, lensless imaging, light field, machine vision and automation, magnetic resonance imaging, metasurface, microplastics, neuromorphic imaging, optical coherence tomography, speckle, super-resolution" | split: ", " %}{% for group in all_groups %}<a href="#{{ group | slugify }}">{{ group }}</a> \| {% endfor %}

<br>

{% for group in all_groups %}
<h3 id="{{ group | slugify }}">#{{ group }}</h3>

<h4>Journal Papers</h4>
{% bibliography -f journal -q @article[groups={{ group }}] %}

<h4>Conference Papers</h4>
{% bibliography -f conf -q @conference[groups={{ group }}] %}

<hr> 
<br>
{% endfor %}
</div>

<!-- Books / Book Chapters -->
<div id="bybook" style="display:none;">
{% bibliography -f book -q @book %}
</div>

<!-- Preprints -->
<div id="inpress" style="display:none;">
{% bibliography -f journal -q @misc %}
</div>

<!-- Display by Type (Default) -->
<div id="bytype" style="display:block;">
## Journal papers
{% bibliography -f journal -q @article[key!=Liu2025JOpt && key!=CPChen2023OE] %}

## Conference
{% bibliography -f conf -q @conference %}

## Editorials
{% bibliography -f journal -q @article[key=Liu2025JOpt || key=CPChen2023OE] %}
</div>

<br>
<br>