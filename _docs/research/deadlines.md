---
layout: doc
title: 截稿日期
order: 10
---

{% capture today %}{{'now' | date: '%Y-%m-%d'}}{% endcapture %}
{% assign deadlines = site.data.deadlines | sort: "deadline" %}

# 截稿日期

<div class="menu">
    <ul class="menu-list">
        {% for this in deadlines %}
        {% capture deadline %}{{this.deadline | date: '%Y-%m-%d'}}{% endcapture %}
        {% if deadline >= today %}
        <li>
            <a href="{{ this.url }}">
                <strong>{{ this.deadline }}</strong> {{ this.conference }} {{ this.description }}
            </a>
        </li>
        {% endif %}
        {% endfor %}
    </ul>
</div>