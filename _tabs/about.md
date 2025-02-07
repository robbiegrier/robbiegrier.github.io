---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

### Work Experience

{% for job in site.data.work %}
#### {{ job.timeframe }}: [**{{ job.name }}**]({{ job.link }})
{{ job.title }}
{% if job.blurb %}
> {{ job.blurb }}
{% endif %}
{% endfor %}

---

### Education

{% for degree in site.data.education %}
#### {{ degree.timeframe }}: **{{ degree.name }}; [{{ degree.university }}]({{ degree.link  }})**
{{ degree.college }}, GPA: {{ degree.gpa }}
{% if degree.blurb %}
> {{ degree.blurb }}
{% endif %}
{% endfor %}