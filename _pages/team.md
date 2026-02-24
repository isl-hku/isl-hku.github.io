---
title: team
layout: default
permalink: /team
excerpt: "Team"
title: "Team"
---

{% assign people_sorted = site.team | sort: 'joined' %}
{% assign role_array = "pi|researcher|postdoc|gradstudent|intern|visiting|others" | split: "|" %}


<h2>Current members</h2>
<div style="align:left;">
{% for role in role_array %}
{% assign role_members = people_sorted | where: "position", role | where_exp: "item", "item.left == nil or item.left == ''" %}

{% if role_members.size > 0 %}
{% for profile in role_members %}
<div class="list-item-people">
<hr>
<p class="list-post-title">
{% if profile.avatar %}
<a href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{ site.url }}{{site.baseurl}}/assets/images/member/{{profile.avatar}}"></a>
{% else %}
<a href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{ site.url }}{{site.baseurl}}/assets/images/member/bio.jpg"></a>
{% endif %}
</p>
<p>
<a class="name" href="{{ site.url }}{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>  
<br>
<span>
{% case role %}
{% when 'pi' %}PI
{% when 'researcher' %}Research Faculty
{% when 'postdoc' %}Postdoc
{% when 'gradstudent' %}Graduate student
{% when 'intern' %}Intern
{% when 'visiting' %}Visiting
{% when 'others' %}Others
{% endcase %}
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
{% endfor %}
{% endif %}
{% endfor %}
</div>

<br>
<hr>

<h2>Alumni</h2>
<div style="align:left;">
{% for role in role_array %}
{% assign role_alumni = people_sorted | where: "position", role | where_exp: "item", "item.left != nil and item.left != ''" | sort: "left" | reverse %}
{% if role_alumni.size > 0 %}
{% for profile in role_alumni %}
{% assign alumni_present = true %}
{% endfor %}
{% endif %}
{% endfor %}

{% if alumni_present %}
<table class="table table-striped" style="width: 100%;">
	<thead>
		<tr>
			<th>Name</th>
			<th>Role</th>
			<th>Years</th>
			<th>Current</th>
		</tr>
	</thead>
	<tbody>
	{% for role in role_array %}
	{% assign role_alumni = people_sorted | where: "position", role | where_exp: "item", "item.left != nil and item.left != ''" | sort: "left" | reverse %}
	{% if role_alumni.size > 0 %}
	{% for profile in role_alumni %}
		<tr>
			<td>
				{{ profile.name }}
			</td>
			<td>
				{% case role %}
				{% when 'pi' %}PI
				{% when 'researcher' %}Research Faculty
				{% when 'postdoc' %}Postdoc
				{% when 'gradstudent' %}Graduate student
				{% when 'intern' %}Intern
				{% when 'visiting' %}Visiting
				{% when 'others' %}Others
				{% endcase %}
			</td>
			<td>{{ profile.joined }}~{{ profile.left }}</td>
			<td>{{ profile.current }}</td>
		</tr>
	{% endfor %}
	{% endif %}
	{% endfor %}
	</tbody>
</table>
{% endif %}
</div>

