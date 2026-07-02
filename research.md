---
layout: default
title: Research
---

<div class="research-page">
    <h1>Research Highlights</h1>
    
    <div class="research-intro-section">
        
        <p class="intro-text">
            My research interests are 1) strategic issues in design & operations of space systems and 2) engineering decision-making problems. These interests are within the theory of <b>Systems Engineering</b> and <b>Operations Research</b>, applied to <b>Space Systems</b>.
        </p>

        <div class="intro-image-centered">
            <img src="{{ '/assets/img/research_overview.png' | relative_url }}" alt="Research Areas Overview">
        </div>
    </div>

    <nav class="section-jump-links" aria-label="Research sections">
        {% for project in site.data.research %}
            <a href="#research-{{ project.title | slugify }}">{{ project.title }}</a>
        {% endfor %}
    </nav>

    <div class="research-list">
        {% for project in site.data.research %}
        <div class="research-item-vertical" id="research-{{ project.title | slugify }}">
            
            <h3 class="research-title">{{ project.title }}</h3>

            <div class="research-img-center">
                {% if project.image %}
                    {% assign media_ext = project.image | split: "." | last | downcase %}
                    {% if media_ext == "mp4" %}
                    <video autoplay muted loop playsinline controls aria-label="{{ project.title }}">
                        <source src="{{ project.image | relative_url }}" type="video/mp4">
                    </video>
                    {% else %}
                    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
                    {% endif %}
                {% endif %}

                {% if project.caption %}
                    <div class="research-caption">
                        {{ project.caption }}
                    </div>
                {% endif %}
            </div>

            <div class="research-content-body">
                
                <div class="research-meta">
                    <span class="research-period">{{ project.period }}</span>
                    {% if project.keywords %}
                        <span class="research-keywords">
                            {% for keyword in project.keywords %}
                                #{{ keyword }} 
                            {% endfor %}
                        </span>
                    {% endif %}
                </div>

                <div class="research-desc">
                    {{ project.description | markdownify }}
                </div>

                {% if project.related_papers %}
                <div class="related-pubs-section">
                    <h4 class="related-pubs-title">Related Publications</h4>
                    <ul class="related-pubs-list">
                        {% for paper_title in project.related_papers %}
                            {% assign matched_pub = site.data.publications | where: "title", paper_title | first %}
                            <li>
                                {% if matched_pub %}
                                    <span class="rel-pub-title-text">
                                        {{ matched_pub.title }}
                                    </span>

                                    <span class="rel-pub-meta">
                                        - {% include publication_meta.html pub=matched_pub %}
                                    </span>

                                    {% unless matched_pub.venue == "in preparation" %}
                                        <a href="{{ '/publications' | relative_url }}#pub-{{ matched_pub.title | slugify }}" class="rel-pub-page-link" aria-label="View publication details for {{ matched_pub.title | escape }}">
                                            <span>Details</span>
                                            <svg aria-hidden="true" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
                                                <path d="M5 12h14"></path>
                                                <path d="m12 5 7 7-7 7"></path>
                                            </svg>
                                        </a>
                                    {% endunless %}
                                {% else %}
                                    <span class="rel-pub-title-text">{{ paper_title }}</span>
                                {% endif %}
                            </li>
                        {% endfor %}
                    </ul>
                </div>
                {% endif %}
            </div>

        </div>
        <hr class="research-divider">
        {% endfor %}
    </div>
</div>
