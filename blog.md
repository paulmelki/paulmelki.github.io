---
layout: page
title: "Life & Thoughts Blog "
permalink: /blog/
---

On this page you may find all my thoughts and ramblings about life in general
and more particularly reviews of the books I read, some quotes or poems I find 
to be extremely beautiful, or some commentaries about our existence.

In addition, you may also find some technical posts about programming, 
machine learning, computer vision, statistics, or other technical stuff I do and 
hope to share with the world! 


<!-- {% assign sorted_cats = site.categories | sort  %}{% for category in sorted_cats %}{% if forloop.last == true %}and {% endif %}<a href="/categories/#{{category[0]}}" style="font-weight:normal;">{{category[0] | camelcase }}</a> ({{ category[1].size  }}){% if forloop.last == false %},{% endif %} {% endfor %} -->



<ul id="archive">
{% for post in site.posts %}
    {% if post.categories contains 'Technicals' %}
    {% else %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <h2 class="blogyear" style="font-family: EB Garamond; font-weight:600;">{{ y}}</h2>
  {% endif %}
<li class="archiveposturl"><span><a style="font-size: larger; font-family: EB Garamond; font-weight: 600;" href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span><br/>
<span class = "postlower">

<!--<strong>Author:</strong> {{post.author}} -->
<strong>Category:</strong>  {% if post.categories %}
 
  {% for cat in post.categories %}
  <a href="/categories/#{{ cat }}" style="font-style:italic;" title="{{ cat }}">{{ cat }}</a>&nbsp;
  {% endfor %}

{% endif %} <!-- {{ post.categories | first }} -->
<strong style="font-size:100%; font-family: 'EB Garamond', sans-serif; float:right; padding-right: .5em">{{ post.date | date: '%d %b %Y' }}</strong> 
</span> 

</li>
{% endif %}
{% endfor %}
</ul>

<!-- {{ post.date | date: '%m %d, %Y' }} -->
