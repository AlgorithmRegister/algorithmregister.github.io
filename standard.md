---
layout: default
title: Algorithmic Transparency Standard
description: Updating the Dutch Algorithmic Transparency Standard
splash: true
orgs: true
---
[//]: # (## About the current standard)

[//]: # (The current version of the [Dutch Algorithmic Transparency Standard](https://standaard.algoritmeregister.org/standard) is 0.2. What this means is that it is still in full development, and you can expect some major changes before it reaches 1.0. Some parts that need work are technical specification of the field types, categorization, internationalization and localization (the possibility to add fields on a local level).)

[//]: # (## What will we be doing)

[//]: # (Our project focusses on making an iteration on the current Dutch Algorithmic Transparency Standard and its documentation. By doing so, we hope and expect to stay compatible, working towards an international standard.)

## v0.3 live preview

We are currently updating the 0.2 version of the Dutch Standard for Algorithmic Transparency. Below is a live preview of the 0.3 version of the standard currently being developed. Colored <span class="attribute required">attributes</span> are required attributes.

There is also a [more technical specification](https://standaard.algoritmeregister.org/overview) for use in combination with the [.csv template for registration](https://standaard.algoritmeregister.org/registration-v0.3.template.csv).

<style>
    h3 {
        border-bottom: 1px solid gray;
    }
    .attribute { 
        background: #E6E6E6;
        color: #555;
        border-radius: 4px;
        padding: 0 4px;
        font-size: 0.8em;
        font-family: monospace
    }
    .required {
        background: #4D80E2;
        color: #fff;
    }
</style>
<div id="data"></div>
<script type="text/html" id="attribute_tmpl">
    <p>
        <b><%=name%> </b><span class="attribute <% if (required) { %>required<% } %>"><%=attr%></span><br>
        <i><%=description%></i>
    </p>
</script>
<script src="/js/microtemplating.js"></script>
<script>
    var url = "https://standaard.algoritmeregister.org/schemas/registration-v0.3.schema.json";
    fetch(url).then(response => response.json()).then(data => render(data));
    function render(data) {
        var resultsEl = document.getElementById("data");
        var category = "";
        for(var i in data.properties) {
            var prop = data.properties[i];
            if (prop.category !== category) {
                category = prop.category;
                resultsEl.innerHTML += `<h3>${category}</h3>`;
            }
            prop.attr = i;
            resultsEl.innerHTML += tmpl("attribute_tmpl", prop);
        }
    }
</script>

<h2 class="my5">More information</h2>

For more information please contact Eurocities:

<a href="https://eurocities.eu/" class="btn display-inline-block mb4">Visit Eurocities website</a>