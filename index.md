---
layout: homepage
---

## About Me

I’m **Gen Shi**, a Ph.D. candidate at Beihang University, advised by Prof. Jie Tian.  
I received my M.Eng. degree from Beijing Institute of Technology in 2022, and the B.Eng. degree from Wuhan University of Technology in 2019.

## Research Interests

- Medical image analysis  
- Graph representation learning  
- Magnetic particle imaging

## News

<ul>
  {% assign news_list = site.data.news | sort: "date" | reverse | slice: 0, 5 %}
  {% for item in news_list %}
    <li>{{ item.date | date: "%Y-%m" }}: {{ item.title }}</li>
  {% endfor %}
</ul>

{% include_relative _includes/publications.md %}

## Selected Honors
<ul>
  {% assign honors = site.data.honors | sort: "sort_key" | reverse %}
  {% for item in honors %}
    <li><em>{{ item.date }}</em>: {{ item.content | strip }}</li>
  {% endfor %}
</ul>

{% include_relative _includes/services.md %}
