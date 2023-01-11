---
layout: default
title: Background
description: The road we traveled.
splash: true
orgs: true
cta-button:
    url: /analysis
    text: "Next: analysing the needs"
---
## Towards a common Algorithmic&nbsp;Transparency&nbsp;Standard

Algorithm registers offer a standardized, searchable and archivable way to document the decisions and assumptions  that were made in the process of developing, implementing, managing, and ultimately dismantling algorithmic applications in public organizations.

For citizens, an algorithm register can be a medium to facilitate participation and it allows them to influence how cities’ use of algorithms impacts their lives. For local governments, it can be a tool to manage AI governance in the development and operation process according to existing public services principles of responsibility, transparency, and security.

At the basis for any (interoperable) algorithm registry is a data schema that determines the scope of information on algorithms and describes the dataset to support common understanding.

### Building on top of existing work

Building on good practice of Amsterdam and Helsinki, and the Dutch Standard for Algorithmic Transparency, DF Lab developed [an updated version of the Algorithmic&nbsp;Transparency&nbsp;Standard](/standard) — a common data schema for algorithm registries; validated, open-source, publicly available, and ready for use in local algorithm registers.

### Approach

Our approach was to introduce the participating cities to the work that had been done in The Netherlands, explore <a href="/analysis">the needs of the participating cities and their local contexts</a>. From there, we did <a href="/analysis">fit-gap analysis</a> and designed a proposed next <a href="/changelog">iteration</a> of the <a href="/standard">standard</a>.

To pilot this proposed data standard in practice, we created an <a href="/template">interview template</a>. Participating cities were encouraged to start making a first inventarory of algorithms in their organizations, and filling in the interview template for a couple of them. We joined them in doing the interviews, and used their feedback to refine the proposed data schema.

## Timeline

<ul>
{% for date in site.data.planning %}
<li>
    <b>{{ date.when }}</b>
    <h2>{{ date.title }}</h2>
    <span class="label">{{ date.type }}</span>
    <p>{{ date.description | markdownify }}</p>
</li>
{% endfor %}
</ul>
