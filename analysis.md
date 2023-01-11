---
layout: default
title: Analysis and feedback
description: Results from the kick-off session, individual interviews and piloting the draft version with the participants.
splash: true
cta-button:
    url: /changelog
    text: "Next: updating the standard"
orgs: true
---
<ul>
<li><a href="#goals">Goals</a></li>
<li><a href="#stakeholders">Stakeholders</a></li>
<li><a href="#use-cases-and-needs">Use cases and needs</a></li>
<li><a href="#local-contexts">Local contexts</a></li>
<li><a href="#fit-gap-analysis">Fit-gap analysis</a></li>
<li><a href="#feedback">Feedback</a></li>
</ul>

<a name="goals"></a>
<h2 class="my5">Goals</h2>

<div>
    {% for item in site.data.goals %}
        <h3>{{ item[0] }}</h3>
        <ul>
        {% for item in item[1] %}
        <li>{{ item }}</li>
        {% endfor %}
        </ul>
    {% endfor %}
</div>

<a name="stakeholders"></a>
<h2 class="my5">Stakeholders</h2>

<ul>
{% for item in site.data.stakeholders %}
<li>{{ item }}</li>
{% endfor %}
</ul>

<a name="use-cases-and-needs"></a>
<h2 class="my5">Use cases and needs</h2>

<a name="local-contexts"></a>
<h2 class="my5">Local contexts</h2>

<a name="fit-gap-analysis"></a>
<h2 class="my5">Fit-gap analysis</h2>

<div>
{% for item in site.data.fit-gap %}
    <p>
        <b>Business requirement</b>: {{ item["Business requirement"] }}<br>
        <b>Existing situation</b>: {{ item["Existing situation"] }}<br>
        <b>Desired situation</b>: {{ item["Desired situation"] }}<br>
        <b>Capabilities needed</b>: {{ item["Capabilities needed to reduce gap"] }}<br>
        {% if item["Issue and risk"] %}<b>Issue and risk</b>: {{ item["Issue and risk"] }}<br>{% endif %}
        {% if item["Suggestion"] %}<b>Suggestion</b>: {{ item["Suggestion"] }}<br>{% endif %}
        {% if item["Available resources"] %}<b>Available resources</b>: {{ item["Available resources"] }}<br>{% endif %}
    </p>
{% endfor %}
</div>

<a name="feedback"></a>
<h2 class="my5">Feedback from the pilot</h2>

<div>
{% for item in site.data.feedback %}
{% endfor %}
</div>