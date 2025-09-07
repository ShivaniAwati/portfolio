---
layout: single
title: "Experience"
permalink: /experience/
toc: false
classes: wide
---

{% for job in site.data.experience %}
<div class="exp-item" id="{{ job.slug | default: job.company | slugify }}">
  <div class="exp-role">{{ job.role }}</div>
  <div class="exp-meta">{{ job.company }} • {{ job.location }} </div>
  <ul class="compact-list">
    {% for b in job.bullets %}
    <li>{{ b }}</li>
    {% endfor %}
  </ul>
  {% if job.tools %}
  <div class="badges">
    {% for t in job.tools %}
    <span>{{ t }}</span>
    {% endfor %}
  </div>
  {% endif %}
</div>
<hr/>
{% endfor %}

