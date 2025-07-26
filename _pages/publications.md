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





<!-- ## Featured -->
<!-- <br> -->
<!-- <div style="text-align:center"> -->
<!-- <a href="https://onlinelibrary.wiley.com/doi/10.1002/lpor.202200828" target="_blank"><img src="{{site.baseurl}}/assets/images/research/lsa.jpg"  style="height:200px; border-radius: 0%; box-shadow: 0px 0px 0px #ffffff00;"></a> -->
<!-- <a href="https://onlinelibrary.wiley.com/doi/10.1002/lpor.202200828" target="_blank"><img src="{{site.baseurl}}/assets/images/research/lpor202308.jpg"  style="height:200px; border-radius: 0%; box-shadow: 0px 0px 0px #ffffff00;"></a>
<a href="https://onlinelibrary.wiley.com/doi/full/10.1002/lpor.202100008" target="_blank"><img src="{{site.baseurl}}/assets/images/research/lpor202106.jpg"  style="height:200px; border-radius: 0%; box-shadow: 0px 0px 0px #ffffff00;"></a>
<a href="https://www.osapublishing.org/prj/home.cfm" target="_blank"><img src="{{site.baseurl}}/assets/images/research/prj.jpg"  style="height:200px; border-radius: 0%;%"></a> -->
<!-- <a href="https://www.journals.elsevier.com/optics-and-lasers-in-engineering" target="_blank"><img src="{{site.baseurl}}/assets/images/research/ole.jpg"  style="height:200px; border-radius: 0%;%"></a> -->
<!-- <a href="https://www.osapublishing.org/oe/home.cfm" target="_blank"><img src="{{site.baseurl}}/assets/images/research/oe.jpg"  style="height:200px; border-radius: 0%;%"></a> -->
<!-- <a href="https://onlinelibrary.wiley.com/doi/10.1002/apxr.202200118" target="_blank"><img src="{{site.baseurl}}/assets/images/research/apxr202302.jpg"  style="height:200px; border-radius: 0%; box-shadow: 0px 0px 0px #ffffff00;"></a>
</div> -->
<!-- <br> -->



<br>

**All keywords:** \| [AI and deep learning](https://www.eee.hku.hk/~elam/research/pub-dl.html) \| [biomedical microscopy](https://www.eee.hku.hk/~elam/research/pub-bio.html) \| [compressed sensing](https://www.eee.hku.hk/~elam/research/pub-cs.html) \| [computational imaging](https://www.eee.hku.hk/~elam/research/pub-ci.html) \| [computational lithography](https://www.eee.hku.hk/~elam/research/pub-litho.html) \| [digital holography](https://www.eee.hku.hk/~elam/research/pub-dh.html) \| [education technology](https://www.eee.hku.hk/~elam/research/pub-ed.html) \| [electronic imaging](https://www.eee.hku.hk/~elam/research/pub-ei.html) \| [eye imaging](https://www.eee.hku.hk/~elam/research/pub-eye.html) \| [lensless imaging](https://www.eee.hku.hk/~elam/research/pub-li.html) \| [light field](https://www.eee.hku.hk/~elam/research/pub-lf.html) \| [machine vision and automation](https://www.eee.hku.hk/~elam/research/pub-ra.html) \| [magnetic resonance imaging](https://www.eee.hku.hk/~elam/research/pub-mri.html) \| [metasurface](https://www.eee.hku.hk/~elam/research/pub-meta.html) \| [microplastics](https://www.eee.hku.hk/~elam/research/pub-env.html) \| [neuromorphic imaging](https://www.eee.hku.hk/~elam/research/pub-uf.html) \| [optical coherence tomography](https://www.eee.hku.hk/~elam/research/pub-oct.html) \| [speckle](https://www.eee.hku.hk/~elam/research/pub-speckle.html) \| [super-resolution](https://www.eee.hku.hk/~elam/research/pub-spr.html) \|

<br>



<!-- Nav -->

<ul class="nav nav-tabs" style="width:100%; margin: 0 auto;">
    <li class="active">
    <a data-toggle="tab"><button id="btn_bytype" onclick="ShowOrHide('bytype')">By Type</button></a>
    </li>
    <li class="">
    <a data-toggle="tab"><button id="btn_byyear" onclick="ShowOrHide('byyear')">By Year</button> </a>
    </li>
    <li class="">
    <a data-toggle="tab"><button id="btn_bybook" onclick="ShowOrHide('bybook')">Book / Book Chapters</button></a>
    </li>
    <li class="">
    <a data-toggle="tab"><button id="btn_bypatent" onclick="ShowOrHide('bypatent')">Patents</button> </a>
    </li>
    <li class="">
    <a data-toggle="tab"><button id="btn_inpress" onclick="ShowOrHide('inpress')">Preprint</button></a>
    </li>
    <!-- <li class="">
    <a data-toggle="tab" href="https://scholar.google.com/citations?hl=en&user=adQED6IAAAAJ&view_op=list_works&authuser=1&sortby=pubdate"><button onclick="window.location.href='https://scholar.google.com/citations?hl=en&user=adQED6IAAAAJ&view_op=list_works&authuser=1&sortby=pubdate';">Google Scholar</button></a>
    </li> -->
</ul>


<br>



{% assign this_year = "now" | date: "%Y"  %}
{% assign years = (1999..this_year) | reverse %}

<script>var byyeartext="year";var bytypetext="type";</script>

<!-- Display by year -->
<div id="byyear" style="display:none;">
{% for y in years %}
  <h3 id="{{y}}">{{y}}</h3>
  {% bibliography -f journal -f conf  -q @*[year={{y}}]* %}
{% endfor %}
</div>



<!-- Patents -->
<div id="bypatent" style="display:none;">

{% bibliography -f others -q @patent %}

</div>


<!-- Book -->
<div id="bybook" style="display:none;">

{% bibliography -f book -q @book %}

</div>

<!-- In Progress -->
<div id="inpress" style="display:none;">

{% bibliography -f journal -q @misc %}

</div>

<!-- Display by type -->
<div id="bytype" style="display:block;">

## Journal papers

{% bibliography -f journal -q @article[key!=Liu2025JOpt && key!=CPChen2023OE]  %}

## Conference

{% bibliography -f conf -q @conference %}


## Editorials

{% bibliography   -f journal -q  @article[key=Liu2025JOpt || key=CPChen2023OE] %}


</div>



