---
layout: default
title: Calendar
---

<table>
<thead>
<tr>
<th align="center"></th>
<th align="left"> </th>
<th align="left" width="70%"> </th>
</tr>
</thead>
<tr>
<td align="center"> <strong>Week</strong> </td>
<td align="left"> <strong>Day</strong> </td>
<td align="left"> <strong>Project</strong> </td>
</tr>
<tr>
<td align="center">  </td>
<td align="left">  </td>
<td align="left">  </td>
</tr>

{% assign sortedposts = site.static['cal'] %}



{% for post in sortedposts %}
	<tr>
	<td align="center"> {{ post.week }} </td>
	<td align="left"> 
	{% if post.day == 1 %}
	Tues
	{% elsif post.day == 2 %}
	Thurs
	{% else %}
	<!-- No day... -->
	{% endif %}
	</td>
	
	{% if post.categories contains 'draft' %}
	<td> ... </td>
	{% else %}
	<td align="left"> 
	<a href="{{ post.url | prepend:site.url | replace:' ','' }} ">{{ post.title }}</a>
	</td>
	{% endif %}
	
	</tr>
{% endfor %}
<tr>
<td align="center"></td>
<td align="left"> </td>
<td align="left"> </td>
</tr>
</table>