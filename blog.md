---
layout: page
title: "Blog: thoughts, ramblings & technical stuff"
permalink: /blog/
---

On this page you may find all my thoughts and ramblings about life in general
and more particularly reviews of the books I read, some quotes or poems I find 
to be extremely beautiful, or some commentaries about our existence. 

**Note:** *No alcohol was consumed before or during the writing of these pieces, though it 
may look otherwise.*

In addition, you may also find some technical posts about programming, 
machine learning, computer vision, statistics, or other technical stuff I do and 
hope to share with the world! 


<!-- {% assign sorted_cats = site.categories | sort  %}{% for category in sorted_cats %}{% if forloop.last == true %}and {% endif %}<a href="/categories/#{{category[0]}}" style="font-weight:normal;">{{category[0] | camelcase }}</a> ({{ category[1].size  }}){% if forloop.last == false %},{% endif %} {% endfor %} -->



<ul id="archive">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <h2 class="blogyear" style="font-family: Staatliches;">{{ y}}</h2>
  {% endif %}
<li class="archiveposturl"><span><a style="font-size: larger; font-family: Staatliches; font-weight: 200;" href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span><br/>
<span class = "postlower">

<!--<strong>Author:</strong> {{post.author}} -->
<strong>Category:</strong>  {% if post.categories %}
 
  {% for cat in post.categories %}
  <a href="/categories/#{{ cat }}" title="{{ cat }}">{{ cat }}</a>&nbsp;
  {% endfor %}

{% endif %} <!-- {{ post.categories | first }} -->
<strong style="font-size:120%; font-family: 'Staatliches', sans-serif; float:right; padding-right: .5em">{{ post.date | date: '%d %b %Y' }}</strong> 
</span> 

</li>
{% endfor %}
</ul>

<!-- {{ post.date | date: '%m %d, %Y' }} -->
