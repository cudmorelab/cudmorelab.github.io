---
title: "Splash Page"
layout: splash
permalink: /
date: 2016-03-23T11:48:41-04:00
hidden: true
header:
  #overlay_color: "#aaa"
  #overlay_filter: "0.5"
  overlay_image: /assets/images/thy1-gfp.jpg
  #actions:
    #- label: "Download"
    #  url: "https://github.com/mmistakes/minimal-mistakes/"
  #caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
#excerpt: "This is an intro/overview paragraph."
intro:
  - excerpt: 'We recently received NIH funding including from the BRAIN initiative and are looking to hire!'
feature_row:
  - image_path: assets/images/unsplash-gallery-image-1-th.jpg
    #alt: "placeholder image 1"
    title: "Juniors Specialist"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    #image_caption: "Image courtesy of [Unsplash](https://unsplash.com/)"
    #alt: "placeholder image 2"
    title: "Graduate Students"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
    #url: "#test-link"
    #btn_label: "Read More"
    #btn_class: "btn--primary"
  - image_path: /assets/images/unsplash-gallery-image-3-th.jpg
    title: "Undergraduates"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
feature_row2:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Left Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Left aligned with `type="left"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row3:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Right Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Right aligned with `type="right"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row4:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Center Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Centered with `type="center"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

<!-- {% include feature_row id="feature_row2" type="left" %} -->

<!-- {% include feature_row id="feature_row3" type="right" %} -->

<!-- {% include feature_row id="feature_row4" type="center" %} -->
