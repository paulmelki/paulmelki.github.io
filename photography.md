---
layout: page
title: Photography
permalink: /photography/
---

Here you can find some collections of my photography :-)

<ul id="archive">
{% for post in site.posts %}
    {% if post.categories contains 'Technicals' %}
    {% else %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <h2 class="blogyear" style="font-family: Courier Prime; font-weight:700;">{{ y}}</h2>
  {% endif %}
<li class="archiveposturl"><span>
<a style="font-size: larger; font-family: Courier Prime; font-weight: 400;" href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
<strong style="font-size:100%; font-family: 'Courier Prime', sans-serif; font-weight:400;  float:right; padding-right: .5em">{{ post.date | date: '%d %b %Y' }}</strong> 
</span>
<br/>
<span class = "postlower">

<!--<strong>Author:</strong> {{post.author}} -->
<!-- <strong>Category:</strong>  {% if post.categories %}
  {% for cat in post.categories %}
  <a href="/categories/#{{ cat }}" style="font-style:italic;" title="{{ cat }}">{{ cat }}</a>&nbsp;
  {% endfor %}
{% endif %} {{ post.categories | first }} -->

</span> 

</li>
{% endif %}
{% endfor %}
</ul>