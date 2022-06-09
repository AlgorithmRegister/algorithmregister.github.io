---
layout: default
title: Planning
description: Roadmap to a shared standard for algorithmic transparency
splash: true
orgs: true
---
## What we will be doing

Our approach is to introduce the participating cities to the work that has been done in The Netherlands, explore the needs of the participating cities and their local contexts. From there, we plan to do a fit-gap analysis and design a proposed next version ("0.3") of the standard.

To test this proposed data standard in practice, we will create an interview template. Participating cities are encouraged to start making a first inventarory of algorithms in their organizations, and filling in the interview template for a couple of them. We'll join them in doing the interviews, and use the feedback from that to refine the proposal.

<ul>
{% for date in site.data.planning %}
<li>
    <b>{{ date.when }}</b>
    <h2>{{ date.title }}</h2>
    <span class="label">{{ date.type }}</span>
    <p>{{ date.description }}</p>
</li>
{% endfor %}
</ul>

<h2 class="my5">More information</h2>

For more information please contact:

<a href="mailto:info@algoritmeregister.org" class="btn display-inline-block mb4">info@algoritmeregister.org</a>
