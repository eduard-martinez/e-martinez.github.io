---
layout: page
title: Ideas
permalink: /ideas/
description: Past and future project, some thoughts and opinions
order: 5
---

<center>
  <h2>Visit my external blog</h2>
  <a href="https://bribigfish.wordpress.com/" target="_blank" style="text-decoration: none;">
    <img src="https://s.w.org/about/images/logos/wordpress-logo-notext-rgb.png" width="50" alt="WordPress logo">
    <br>
    <strong>bribigfish.wordpress.com</strong>
  </a>
</center>

<iframe src="https://bribigfish.wordpress.com" width="100%" height="600px" style="border:none;"></iframe>


<!--Tags generator-->
{% assign all_tags = '' | split: ',' %}

 {% for post in site.categories.idea %}
    {% for tags in post.tags %}
        {% for tag in tags %}
            {% assign all_tags = all_tags | push: tag %}
        {% endfor %}
    {% endfor %}
{% endfor %}

{% assign all_tags = all_tags | sort %}
{% assign all_tags = all_tags | uniq %}


<!--TagCloud-->
<center> <br><br>
{% include tagcloud.html %}
</center>


