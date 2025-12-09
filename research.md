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

    <div class="research-list">
        {% for project in site.data.research %}
        <div class="research-item-vertical">
            
            <h3 class="research-title">{{ project.title }}</h3>

            <div class="research-img-center">
                {% if project.image %}
                    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
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
                            {% if matched_pub %}
                            <li>
                                <span class="rel-pub-title-text">
                                    {{ matched_pub.title }}
                                </span>
                                
                                <span class="rel-pub-meta">
                                    - {{ matched_pub.venue }}{% if matched_pub.year %}, {{ matched_pub.year }}{% endif %}
                                </span>

                                {% if matched_pub.link or matched_pub.pdf %}
                                <a href="{{ matched_pub.link | default: matched_pub.pdf }}" target="_blank" class="rel-pub-link-icon" title="View Publication">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
                                </a>
                                {% endif %}
                            </li>
                            {% endif %}
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