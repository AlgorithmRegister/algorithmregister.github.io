---
layout: default
title: Algorithmic Transparency Standard
description: Version 0.3.1 (beta)
splash: true
orgs: false
#cta-button:
#    url: /plans
#    text: "Next: plans for 2023"
---
## About the standard

The Algorithmic Transparency Standard is a set of shared categories of information that cities
can use to help people understand how the algorithms used in local administrations work, and
what their purpose is. It also allows people to compare different algorithms within and across
cities. This standard supports documenting decisions and assumptions for both
management of artificial intelligence (AI) governance and provide meaningful
transparency in a standardized way. To learn more about what the standard is and how it
works, read our [guidance page](/guidance).

[//]: # The Algorithmic Transparency Standard is created to support documenting decisions and assumptions for both management of AI governance and providing meaningful transparency in a standardized way.

Below is a live preview of the current data schema, version 0.3.1 (beta). It contains the
categories of information that cities should fill in about their algorithms to create a clear and
comparable overview. These fields refer to different phases of the algorithm life cycle. Required attributes are coloured <span class="attribute required">blue</span>.

Once you feel comfortable with the categories and descriptions, please download the [.csv template](https://www.algoritmeregister.org/standard/registration-v0.3.1.template.csv) or the [Excel template](https://www.algoritmeregister.org/standard/registration-v0.3.1.template.xlsx) and fill in the information in relation to your city. When you are happy that the information is complete, the idea is for you to upload it on your own public website for full transparency. A complete overview of how to fill in the template is available on our [guidance page](/guidance).

[//]: # Below is a live preview of the current data schema, version 0.3.1 (beta). It contains the fields that can be documented during the different phases of the algorithm life cycle, together with their descriptions. Required attributes are colored <span class="attribute required">blue</span>. Please use in combination with the [.csv template](https://www.algoritmeregister.org/standard/registration-v0.3.1.template.csv) or the [Excel template](https://www.algoritmeregister.org/standard/registration-v0.3.1.template.xlsx).

For technical users, a [json schema file](https://www.algoritmeregister.org/standard/schemas/registration-v0.3.1.schema.json) is also available.

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
    @media print {
        .notes {
            display: block !important;
            height: 150px;
            width: 100%;
            border: 1px solid gray;
            margin-bottom: 10px;
            break-inside: avoid;
        }
        footer, img, nav, #eurocities {
            display: none !important;
        }
    }
</style>
<div id="data"></div>
<script type="text/html" id="attribute_tmpl">
    <div>
        <a name="<%=attr%>"></a>
        <p style="border-left: 10px solid #F4FAFF; padding-left: 10px; margin-bottom: 2em">
            <b><%=name%></b><br>
            <a href="#<%=attr%>"><span class="attribute <% if (required) { %>required<% } %>"><%=attr%></span></a>
            (<%=type%>, <% if (!required) { %>not<% } %> required)<br>
            <%=description.replace(/((http|https|ftp):\/\/[\w?=&.\/-;#~%-]+(?![\w\s?&.\/;#~%"=-]*>))/g, "<a href='$1' target='_blank'>$1</a>")%>

            <% if (type === "enum") { %>
            <br><br>Possible values: <%=(obj.enum+'').replace(/\,/g, ", ")%>
            <% } %>

            <% if (type === "const") { %>
            <br><br>This value should always be <%=obj.const%> if you are using this version of the Standard.
            <% } %>
        </p>
    </div>
    <div class="notes" style="display: none">
        <span class="attribute <% if (required) { %>required<% } %>"><%=attr%></span>
    </div>
</script>
<script src="/js/microtemplating.js"></script>
<script>
    var url = "https://standaard.algoritmeregister.org/schemas/registration-v0.3.1.schema.json";
    fetch(url).then(response => response.json()).then(data => render(data));
    function render(data) {
        var resultsEl = document.getElementById("data");
        var category = "";
        for(var i in data.properties) {
            var prop = data.properties[i];
            if (prop.category !== category) {
                category = prop.category;
                resultsEl.innerHTML += `<h3>CATEGORY: ${category}</h3>`;
            }
            prop.attr = i;
            if (prop.enum) prop.type = "enum";
            if (prop.const) prop.type = "const";
            if (prop.format) prop.type = prop.format;
            resultsEl.innerHTML += tmpl("attribute_tmpl", prop);
        }
        
        // jump to hash
        var hash = window.location.hash;
        if (hash) location.href = hash;
    }
</script>
