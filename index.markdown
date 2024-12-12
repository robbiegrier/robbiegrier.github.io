---
layout: homepage
---

<link rel="stylesheet" href="css/main.css">

{% for project in site.data.projects %}
# {{ project.name }}

{% if project.blurb %}
{{ project.blurb }}
{% endif %}

{% assign linkKeys = "" | split: ',' %}
{% assign linkVals = "" | split: ',' %}

{% if project.links %}
    {% assign lenLinksm1 = project.links | size | minus:1 %}
    {% for idx in (0..lenLinksm1) %}
        {% assign linkKeys = linkKeys | push: project.links[idx].name %}
        {% assign linkVals = linkVals | push: project.links[idx].link %}
    {% endfor %}
{% endif %}

{% assign len = linkKeys | size %}
{% assign lenm1 = len | minus: 1 %}
{% assign linksStr = "" %}
{% for i in (0..len) %}
    {% assign linksStr = linksStr | append: "[" | append: linkKeys[i] | append: "]" | append: "(" | append: linkVals[i] | append: ")" %}
    {% if i < lenm1 %}
        {% assign linksStr = linksStr | append: " | " %}
    {% endif %}
{% endfor %}

{% assign len = linksStr | size %}
{% if len > 0 %}
## {{ linksStr }}
{% endif %}

{% if project.video_id %}
<iframe width="560" height="315" src="https://www.youtube.com/embed/{{ project.video_id }}" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
{% endif %}

{% if project.embed %}
{{ project.embed }}
{% endif %}

---

{% endfor %}

## Undergrad Work

### Software Development
- [Tinker Engine](https://grier.hashnode.dev/tinker-engine)
- [Boomerblade](https://boomerblade.wixsite.com/boomerblade)
- [Full Portfolio](https://robbiegrier.wixsite.com/portfolio)
