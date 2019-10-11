---
layout: default
title: Build History
permalink: /builds/
---

<div class="home">

    {%- if site.posts.size > 0 -%}
        <h2 class="post-list-heading">Build history</h2>
        <ul class="post-list">
            {% assign weeklyBuilds = site.posts | where: "layout", "weeklyBuild" %}
            {%- for post in weeklyBuilds -%}
                <li>
                    <a class="post-link" href="{{ post.url | relative_url }}">
                        {{ post.title | escape }}
                    </a>
                    
                    {%- if post.summary -%}
                        {{ post.summary }}
                        <br>
                    {%- endif -%}

                    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
                    <span class="post-meta">{{ post.date | date: date_format }}</span>


                </li>
            {%- endfor -%}
        </ul>
    {%- endif -%}

</div>