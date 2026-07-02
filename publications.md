---
layout: default
title: Publications
---

<div class="publications-page">
    <h1>Publications</h1>
    <p>
        (* Corresponding authors underlined)
    </p>

    <nav class="section-jump-links" aria-label="Publication sections">
        <a href="#journal-articles">Journal</a>
        <a href="#work-in-progress">Work in Progress</a>
        <a href="#conference-proceedings">Conference</a>
    </nav>

    <h2 id="journal-articles" class="category-header">Journal Articles</h2>
    <div class="publication-list">
        {% assign journals = site.data.publications | where: "type", "journal" %}
        {% for pub in journals %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>

    <h3 class="subcategory-header">Written in Korean</h3>
    <div class="publication-list">
        {% assign korean_journals = site.data.publications | where: "type", "journal_korean" %}
        {% for pub in korean_journals %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>

    <h2 id="work-in-progress" class="category-header">Preprints & Work in Progress</h2>
    <div class="publication-list">
        {% assign preprints = site.data.publications | where: "type", "preprint" %}
        {% for pub in preprints %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>

    <h2 id="conference-proceedings" class="category-header">Refereed Conference Proceedings</h2>
    <div class="publication-list">
        {% assign conferences = site.data.publications | where: "type", "conference" %}
        {% for pub in conferences %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>

    <h3 class="subcategory-header">Written in Korean</h3>
    <div class="publication-list">
        {% assign korean_conferences = site.data.publications | where: "type", "conference_korean" %}
        {% for pub in korean_conferences %}
            {% include publication_item.html pub=pub %}
        {% endfor %}
    </div>
</div>
