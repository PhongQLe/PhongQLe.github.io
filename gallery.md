---
layout: page
title: Gallery
icon: fa-image
order: 3
permalink: /main/gallery/
---

{% assign image_files = site.static_files | where: "gallery_images", true %}
<div class="slideshow-container">

  <!-- Full-width images with number text -->
  {% for anImage in image_files %}
  <div class = "slideshow-large-display">
    <div class="slideshow-numbertext">{{forloop.index}} / {{image_files.size}}</div>
    <img src="{{anImage.path}}" style="width:100%">
  </div>
  {% endfor %}

  <!-- Next and previous buttons -->
  <a class="slideshow-prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="slideshow-next" onclick="plusSlides(1)">&#10095;</a>

  <!-- Image text -->
  <div class="slideshow-caption-container"> 
    <span id="slideshow-caption"></span>
  </div>


  <!-- Thumbnail images -->
  <div class="slideshow-row">
  {% for anImage in image_files %}
    <div class="slideshow-column">
      <img class="slideshow-demo slideshow-cursor" src="{{anImage.path}}" style="width:100%" onClick="currentSlide({{forloop.index}})" alt="{{ anImage.name | remove: ".jpg" }}">
    </div>
  {% endfor %}
  </div>
</div>

[jekyll-organization]: https://github.com/jekyll
