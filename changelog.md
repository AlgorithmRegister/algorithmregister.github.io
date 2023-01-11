---
layout: default
title: Changelog
description: Keeping track of the changes made.
splash: true
orgs: true
cta-button:
    url: /standard
    text: "Next: start using the standard"
---
{% for item in site.data.changes %}
<h3 style="margin-bottom: 0">{{ item.change }}</h3>
<p>{{ item.rationale }}</p>
{% endfor %}