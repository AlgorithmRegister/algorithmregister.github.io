---
layout: default
title: Algorithmic Transparency Standard
description: Version 0.3 (beta)
splash: true
orgs: false
#cta-button:
#    url: /plans
#    text: "Next: plans for 2023"
---
## About the standard

The Standard for Algorithmic Transparency was created to support documenting decisions and assumptions for both management of AI governance and providing meaningful transparency in a standardized way.

Below is a live preview of the data schema. It contains the fields that can be documented during the different phases of the algorithm life cycle, together with their descriptions. Required attributes are colored <span class="attribute required">blue</span>.

There is also a [more technical specification](https://standaard.algoritmeregister.org/overview) for use in combination with the [.csv template for registration](https://standaard.algoritmeregister.org/registration-v0.3.template.csv), and a [json schema file](https://standaard.algoritmeregister.org/schemas/registration-v0.3.schema.json) for technical users.

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
