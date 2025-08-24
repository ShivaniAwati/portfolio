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

## HCM Weekly Hours Automation {#hcm-weekly-hours-automation}
**Timeline:** Sep 2021 – Nov 2023 (Capgemini)  
**Stack:** Oracle Cloud HCM, Oracle SQL/PLSQL, Oracle Integration Cloud (OIC)

**Problem:** Managers were getting a full employee dump each week. They needed an **automated** report showing only hourly / salaried-hourly employees who actually worked that week, in a fixed template.

### Conclusion / Impact
- Automated end-to-end weekly extract and delivery → reduced manual triage by ~**80%**; cut report turnaround from hours to minutes.
- Improved accuracy with deterministic eligibility logic and ISO-week windowing; fewer corrections and support tickets.
- Added exception reporting (zero-hours, missing timesheets, outliers) that enabled proactive fixes.

### Key Challenges
- Week boundary alignment (time zones, holidays), and partial employment dates.
- Edge cases: rehires, multiple assignments, duplicate rows, employees with no timesheets.
- Reliable scheduling, retries, and **secure delivery** (SFTP/email) with audit trail.

### Techniques Used
- **HCM Extract** with parameterized `:week_start` / `:week_end`:
  - Weekly aggregation using `TRUNC(t.work_date,'IW')` and `SUM(t.hours_worked)`.
  - Eligibility filter: `e.emp_type IN ('HOURLY','SALARIED_HOURLY')` and `HAVING SUM(t.hours_worked) > 0`.
  - Zero-hours audit via `LEFT JOIN` and `HAVING NVL(SUM(t.hours_worked),0)=0`.
- **OIC Integration** to trigger the extract on a schedule, format CSV/text to the client template, and deliver to stakeholders; error handling + notifications.
- **Validation & Monitoring**
  - SQL cross-checks vs. source tables; duplicate and completeness checks; date window alignment.
  - 20% drop detector using a 4-week rolling average to flag abnormal department-level changes.
- **Visualization (optional)**: prototype Tableau view with week filter, top/bottom hours by employee, and department trend.
