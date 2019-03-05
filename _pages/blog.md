---
layout: default
title: Blog
permalink: /blog
---
  <div  id="blog-list" class="container-fluid">
    <div class="row pt-5">
      <div class="col">&nbsp;</div>
      <div class="col">
        <h1>Blog Posts</h1>
      </div>
    </div>
    <div class="row py-5">
      <div class="col">&nbsp;</div>
      <div class="col">
          Read about the latest things I've been working on.
      </div>
    </div>
  </div>

<section class="email-block">
<div class="container-fluid bg-info m-0">
  <div class="row py-5">
    <div class="col-md-12">
      <p>blah</p>
    </div>
  </div>
</div>
</section>


<h2>Categories</h2>
<ul>
{% assign categories_list = site.categories %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %}
      <li><a href="#{{ category }}">{{ category | capitalize }} ({{ site.tags[category].size }})</a></li>
    {% endfor %}
  {% else %}
    {% for category in categories_list %}
      <li><a href="#{{ tag[0] }}">{{ category[0] | capitalize }} ({{ category[1].size }})</a></li>
    {% endfor %}
  {% endif %}
{% assign categories_list = nil %}
</ul>

{% for tag in site.categories %}
  <h3 id="{{ tag[0] }}">{{ tag[0] | capitalize }}</h3>
  <ul>
    {% assign pages_list = tag[1] %}
    {% for post in pages_list %}
      {% if post.title != null %}
      {% if group == null or group == post.group %}
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }} - <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></span></a></li>
      {% endif %}
      {% endif %}
    {% endfor %}
    {% assign pages_list = nil %}
    {% assign group = nil %}
  </ul>
{% endfor %}


<section class="blog-post-list">
<div class="container-fluid m-0">
  <div class="row p-1">
{% for post in site.posts %}

    <div class="col-md-4 col-sm-12 p-1">
      <div class="card blog-card shadow m-2">
        <div>
          <a href="{{ post.url }}"><img src="{{ post.image_thumb }}" style="width:100%" class="w3-margin-bottom"></a>
        </div>
        <div class="p-3">
          <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
          <p>{{ post.author }} - {{ post.date | date: "%d %b %Y" }}</p>

          <div>
            {{ post.excerpt }}
          </div>
          <div>
            <a class="btn btn-primary" href="{{ post.url }}"><span class="buttontext">Read more</span></a>
          </div>
        </div>
      </div>
    </div>

{% endfor %}
  </div>
</div>
</section>
