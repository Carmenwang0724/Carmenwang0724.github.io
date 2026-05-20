---
layout: page
title: "Carmen Wang — Info Sheet"
permalink: /students/carmen-wang/
---

{% assign s = site.data.students.carmen_wang %}

## Basic Info

- **Name:** {{ s.name }}
- **Grade:** {{ s.grade }}
- **High School:** {{ s.high_school }}
- **Unweighted GPA:** {{ s.gpa.unweighted }}

## Test Scores

- **SAT ({{ s.test_scores.SAT.date }}):** {{ s.test_scores.SAT.composite }} ({{ s.test_scores.SAT.sections.math }} + {{ s.test_scores.SAT.sections.evidence_based_reading_writing }})

## Intended Majors

{% for m in s.intended_majors %}
- {{ m }}
{% endfor %}

## Top Activities (summary)

{% for e in s.extracurriculars limit:6 %}
- **{{ e.title }}**{% if e.instrument %} — {{ e.instrument }}{% endif %}{% if e.years %} ({{ e.years }} years){% endif %}
{% endfor %}

## Honors

{% for h in s.honors %}
- {{ h }}
{% endfor %}

## Notes

- {{ s.transcript_note }}
- Self-evaluation: {{ s.self_evaluation }}

If you'd like, I can generate a resume-ready activity bullet list, short essays for any of the projects, or a one-page resume from this data.
