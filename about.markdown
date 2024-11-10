---
layout: page
title: "About Me"
permalink: /about/
menu: main
---

<link rel="stylesheet" href="../css/main.css">

### Work Experience

{% for job in site.data.work %}
#### {{ job.timeframe }}: **{{ job.name }}**
{{ job.title }}
{% if job.blurb %}
> {{ job.blurb }}
{% endif %}
{% endfor %}

---

### Education

{% for degree in site.data.education %}
#### {{ degree.timeframe }}: **{{ degree.name }}; {{ degree.university }}**
{{ degree.college }}, GPA: {{ degree.gpa }}
{% if degree.blurb %}
> {{ degree.blurb }}
{% endif %}
{% endfor %}

