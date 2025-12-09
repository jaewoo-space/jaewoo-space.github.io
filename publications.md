---
layout: default
title: Publications
---

<div class="publications-page">
    <h1>Publications</h1>
    <p>
        (* Corresponding author underlined)
    </p>

    <h2 class="category-header">Preprints & Work in Progress</h2>
    <div class="publication-list">
        {% assign preprints = site.data.publications | where: "type", "preprint" %}
        {% for pub in preprints %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>

    <h2 class="category-header">Journal Articles</h2>
    <div class="publication-list">
        {% assign journals = site.data.publications | where: "type", "journal" %}
        {% for pub in journals %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>

    <h2 class="category-header">Refereed Conference Proceedings</h2>
    <div class="publication-list">
        {% assign conferences = site.data.publications | where: "type", "conference" %}
        {% for pub in conferences %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>
</div>