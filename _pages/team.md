---
title: team
layout: default
permalink: /team
excerpt: "Team"
title: "Team"
---

{% assign people_sorted = site.team | sort: 'joined'  %}
{% assign role_array = "pi|researcher|postdoc|gradstudent|intern|visiting|others|alumni" | split: "|" %}

<h2>Current members</h2>
<div style="align:left;">
{% for role in role_array %}
{% assign people_in_role = people_sorted | where: 'position', role %}

{% if role != 'alumni' %}
{% for profile in people_sorted %}
{% if profile.position contains role %}

<div class="list-item-people">
<hr>
<p class="list-post-title">
{% if profile.avatar %}
<a href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail"  src="{{ site.url }}{{site.baseurl}}/assets/images/member/{{profile.avatar}}"></a>
{% else %}
<a href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail"  src="{{ site.url }}{{site.baseurl}}/assets/images/member/bio.jpg"></a>
{% endif %}
</p>
<p>
<a class="name" href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>  
<br>
<span>
{% if profile.position=='pi' %}
{% assign pos = 'PI' %}
{% elsif profile.position=='researcher' %}
{% assign pos = 'Research Faculty' %}
{% elsif profile.position=='postdoc' %}
{% assign pos = 'Postdoc' %}
{% elsif profile.position=='gradstudent' %}
{% assign pos = 'Graduate student' %}
{% elsif profile.position=='visiting' %}
{% assign pos = 'Visiting' %}
{% elsif profile.position=='intern' %}
{% assign pos = 'Intern' %}
{% elsif profile.position=='others' %}
{% assign pos = 'Others' %}
{% endif %}
{{ pos }} 
<!-- {{ pos }} since {{ profile.joined }} -->
</span>  
</p>
<p style="text-align:left;">
{% if profile.email %}
<a href="mailto:{{ profile.email }}"><i class="fa fa-envelope fa-align-left fa-lg"></i></a> 
{% endif %}
{% if profile.scholar  %}
<a href="{{ profile.scholar }}"><i class="ai ai-google-scholar icon-align-left fa-lg" ></i></a>
{% endif %}
{% if profile.web %}
<a href="{{ profile.web }}"><i class="fa fa-globe fa-align-left fa-lg"></i></a> 
{% endif %}
{% if profile.github  %}
<a href="https://github.com/{{ profile.github }}"><i class="fa fa-github fa-align-left fa-lg"></i></a>
{% endif %}
{% if profile.orcid  %}
<a href="https://orcid.org/{{ profile.orcid }}"><i class="ai ai-orcid icon-align-left fa-lg" ></i></a> 
{% endif %}
{% if profile.twitter  %}
<a href="https://twitter.com/{{ profile.twitter }}"><i class="fa fa-twitter fa-align-left fa-lg"></i></a>
{% endif %}
{% if profile.linkedin  %}
<a href="https://www.linkedin.com/in/{{ profile.linkedin }}"><i class="fa fa-linkedin fa-align-left fa-lg"></i></a>
{% endif %}
</p>
</div>
{% endif %}
{% endfor %}

{% endif %}
{% endfor %}

</div>

<br>
<hr>

<h2>Alumni</h2>

{% for role in role_array %}
{% assign people_in_role = people_sorted | where: 'position', role %}

{% if role == 'alumni' %}

{% for profile in people_sorted %}
{% if profile.position contains role %}

<div class="list-item-people">
<hr>
<p class="list-post-title">
{% if profile.avatar %}
<a href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail"  src="{{ site.url }}{{site.baseurl}}/assets/images/member/{{profile.avatar}}"></a>
{% else %}
<a href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail"  src="{{ site.url }}{{site.baseurl}}/assets/images/member/bio.jpg"></a>
{% endif %}
</p>
<p>
<a class="name" href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a> 
<br> 
<span>
{% if profile.previous=='pi' %}
{% assign pos = 'PI' %}
{% elsif profile.previous=='researcher' %}
{% assign pos = 'Researcher' %}
{% elsif profile.previous=='postdoc' %}
{% assign pos = 'Postdoc' %}
{% elsif profile.previous=='gradstudent' %}
{% assign pos = 'Graduate Student' %}
{% elsif profile.previous=='visiting' %}
{% assign pos = 'Visiting' %}
{% elsif profile.previous=='others' %}
{% assign pos = 'Others' %}
{% endif %}
{{ pos }} ({{ profile.joined }}~{{ profile.left }})
</span> 
<br>
Current: <span>{{ profile.current }}</span> 
</p>
<p style="text-align:left;">
{% if profile.email %}
<a href="mailto:{{ profile.email }}"><i class="fa fa-envelope fa-align-left fa-lg"></i></a> 
{% endif %}
{% if profile.scholar %}
<a href="{{ profile.scholar }}"><i class="ai ai-google-scholar icon-align-left fa-lg" ></i></a>
{% endif %}
{% if profile.web %}
<a href="{{ profile.web }}"><i class="fa fa-globe fa-align-left fa-lg"></i></a> 
{% endif %}
{% if profile.github  %}
<a href="https://github.com/{{ profile.github }}"><i class="fa fa-github fa-align-left fa-lg"></i></a>
{% endif %}
{% if profile.orcid %}
<a href="https://orcid.org/{{ profile.orcid }}"><i class="ai ai-orcid icon-align-left fa-lg" ></i></a> 
{% endif %}
{% if profile.twitter %}
<a href="https://twitter.com/{{ profile.twitter }}"><i class="fa fa-twitter fa-align-left fa-lg"></i></a>
{% endif %}
{% if profile.linkedin  %}
<a href="https://www.linkedin.com/in/{{ profile.linkedin }}"><i class="fa fa-linkedin fa-align-left fa-lg"></i></a>
{% endif %}
</p>
</div>    
{% endif %}
{% endfor %}

{% endif %}
{% endfor %}

<br><br>

<hr>


<!-- ## Former Members of DISP


| Name                        | Role                  | Year |
| --------------------------- | --------------------- | ---- |
| Steve Feller                | AWARE project manager |      |
| Leah Goldsmith              | group administrator   |      |
| Dr. Mehadi Hassan           |                       |      |
| Dr. Ruoyu Zhu               |                       |      |
| Dr. Daniel Marks            |                       |      |
| Dr. Joel Greenberg          | CAXI program leader   |      |
| Dr. Ken MacCabe             |                       |      |
| Paul Vosburgh               | instrument maker      |      |





 -->
