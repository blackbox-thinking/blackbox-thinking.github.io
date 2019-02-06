---
layout: default
title: Blog
permalink: /blog
---
  <div  id="blog-list" class="container-fluid">
    <div class="row pt-5">
      <div class="col-md-6">&nbsp;</div>
      <div class="col-md-6 animated fadeInDownBig">
        <h1>Blog Posts</h1>
      </div>
    </div>
    <div class="row py-5">
      <div class="col-md-6">&nbsp;</div>
      <div class="col-md-6 animated fadeInRightBig">
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

<section class="blog-post-list">
<div class="container-fluid m-0">
{% for post in site.posts %}
  <div class="row py-5">
    <div class="col">
        <p>{{ post.date | date: "%-d %b  %Y" }}</p>
        <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
        <div>
        <p>{{ post.excerpt }}</p>
        <button type="button" class="w3-button w3-theme-d1 w3-margin-bottom"><i class="fa fa-thumbs-up"></i>  Like</button>
        <button type="button" class="w3-button w3-theme-d2 w3-margin-bottom"><i class="fa fa-comment"></i>  Comment</button>
        </div>
    </div>
  </div>

  <div class="card" style="width:400px">
  <img class="card-img-top" src="img_avatar1.png" alt="Card image">
  <div class="card-body">
    <h4 class="card-title">John Doe</h4>
    <p class="card-text">Some example text.</p>
    <a href="#" class="btn btn-primary">See Profile</a>
  </div>
</div>
{% endfor %}
</div>
</section>





<p>subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

