---
layout: default
title: Blog
permalink: /blog
---
  <!-- Page Content -->
  <div class="container">

    <div class="row">

      <!-- Blog Entries Column -->
      <div class="col-md-8">

        <h1 class="my-4">Blog Posts</h1>
        <h1> <small>A view in to the world of industry experts</small></h1>

        <!-- Blog Post -->

{% for post in site.posts %}

        {% capture post_categories %}
        {% for category in post.categories %}'{{ category }}'{% unless forloop.last %},{% endunless %}{% endfor %}
        {% endcapture %}

        <div class="card mb-4" data-categories="{{ post_categories }}">
          <a href="{{ post.url }}">
            <img class="card-img-top blog_img" src="{{ site.img_root }}/{{ post.image_head }}" width="750" height="250" alt="Card image cap">
          </a>
          <div class="card-body">
            <h2 class="card-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
            <p class="card-text">{{ post.excerpt }}</p>
            <a href="{{ post.url }}" class="btn btn-primary">Read More &rarr;</a>
          </div>
          <div class="card-footer text-muted">
            Posted on {{ post.date | date: "%d %b %Y" }} by
            <a href="#">{{ post.author }}</a>
          </div>
        </div>

{% endfor %}

        <!-- Pagination -->
        <ul class="pagination justify-content-center mb-4">
          <li class="page-item">
            <a class="page-link" href="#">&larr; Older</a>
          </li>
          <li class="page-item disabled">
            <a class="page-link" href="#">Newer &rarr;</a>
          </li>
        </ul>

      </div>

      <!-- Sidebar Widgets Column -->
      <div class="col-md-4">

        <!-- Categories Widget -->
        <div class="card my-4 position-fixed">
          <h5 class="card-header">Categories</h5>
          <div class="card-body">
            <div class="row">
              <div class="col-lg-6">
                <ul class="list-unstyled mb-0">
                  <li>
                    <a href="#">Web Design</a>
                  </li>
                  <li>
                    <a href="#">HTML</a>
                  </li>
                  <li>
                    <a href="#">Freebies</a>
                  </li>
                </ul>
              </div>
              <div class="col-lg-6">
                <ul class="list-unstyled mb-0">
                  <li>
                    <a href="#">JavaScript</a>
                  </li>
                  <li>
                    <a href="#">CSS</a>
                  </li>
                  <li>
                    <a href="#">Tutorials</a>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>

        <!-- Side Widget -->
        {% comment %}
        <div class="card my-4">
          <h5 class="card-header">Side Widget</h5>
          <div class="card-body">
            You can put anything you want inside of these side widgets. They are easy to use, and feature the new Bootstrap 4 card containers!
          </div>
        </div>
        {% endcomment %}
      </div>

    </div>
    <!-- /.row -->

  </div>
  <!-- /.container -->
