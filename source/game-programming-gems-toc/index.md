---
layout: default
title: "game-programming-gems-toc"
date: 2013-10-26 10:34
comments: true
sharing: true
footer: true
---

<p>TESTING</p>
 
<ul class="posts">
{% for post in site.pages sort_by:title order:ascending %}
    {% for tag in post.tags %}
        {% if tag == "game programming gems" %}
            <div class="post_info">
                <li>
                    <a href="{{ post.url }}">{{ post.title }}</a> 
                    <span>({{ post.date | date:"%Y-%m-%d" }})</span>
                </li>
            </div>
        {% endif %}
    {% endfor %}
{% endfor %}
</ul>
