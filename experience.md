---
layout: single
title: "Experience"
permalink: /experience/
toc: false
---

{% for job in site.data.experience %}
<div class="exp-item">
  <div class="exp-role">{{ job.role }}</div>
  <div class="exp-meta">{{ job.company }} • {{ job.location }} • {{ job.start }} – {{ job.end }}</div>
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
