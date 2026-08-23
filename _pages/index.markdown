---
layout: default-full
title: "IDA 2027"
header_title: "IDA 2027"
subtitle: "25th International Symposium on Intelligent Data Analysis <br><span class=\"small\">April 22-24, 2027</span> | Pisa, Italy"
header_type: hero
header_img: /assets/images/ida2027-hero.jpg
project_links:
    - url: '/registration/' 
      icon: fas fa-ticket-alt        # Icona del biglietto d'ingresso
      label: Register Now      
    - url: '/regular-paper-track/' 
      icon: fas fa-paper-plane       # Icona aeroplanino di carta (invio)
      label: Submit Paper
---

<div class="container-lg mt-4">
    <div class="row mb-5">
        <div class="col-6">
            <h3>25th International Symposium on Intelligent Data Analysis</h3>
            <p>
                Advancing <em>Intelligent Data Analysis</em> requires novel, potentially game-changing ideas. 
                IDA's mission is to promote ideas over performance: a solid motivation can be as convincing as 
                exhaustive empirical evaluation. Therefore IDA accepts all inspiring papers for both presentation 
                and publication. In order to create an open atmosphere that encourages discussion, the IDA 
                symposium is intentionally small-scale and single-track.
            </p>
            <p>
                The 25th International Symposium on Intelligent Data Analysis will bring together researchers 
                and practitioners from academia, industry, and government to present and discuss the latest 
                research in intelligent data analysis.
            </p>
        </div>
        <div class="col-6">
            <table class="table">
                <thead>
                    <tr>
                        <th style="width: 200px;">Key Date</th>
                        <th style="width: 65%;">Event</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>{{ site.data.dates.abstract_deadline.display }}</td>
                        <td>Abstract Deadline</td>
                    </tr>
                    <tr>
                        <td>{{ site.data.dates.submission_deadline.display }}</td>
                        <td>Submission Deadline</td>
                    </tr>
                    <tr>
                        <td>{{ site.data.dates.decision_notification.display }}</td>
                        <td>Decision Notification</td>
                    </tr>
                    <tr>
                        <td>{{ site.data.dates.camera_ready_deadline.display }}</td>
                        <td>Camera-Ready Deadline</td>
                    </tr>
                    <tr>
                        <td>{{ site.data.dates.early_registration_deadline.display }}</td>
                        <td>Early Registration Deadline</td>
                    </tr>
                    <tr>
                        <td>{{ site.data.dates.symposium_date.display }}</td>
                        <td>Symposium</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
    {% if site.data.sponsors %}
    <div class="row mb-5">
        <div class="col-lg-12">
            <h3 class="mb-4">Sponsors & Supporters</h3>
            <div class="partners-grid" style="grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));">
                {% for sponsor in site.data.sponsors %}
                <a href="{{ sponsor.url }}" target="_blank" class="partner-item-link">
                    <div class="partner-item partner-{{ sponsor.tier }}">
                        <div class="partner-logo-wrapper">
                            {% if sponsor.logo != "" %}
                            <img src="{{ sponsor.logo | relative_url }}" alt="{{ sponsor.name }}" class="partner-logo">
                            {% else %}
                            <svg xmlns="http://www.w3.org/2000/svg" width="400" height="200" viewBox="0 0 400 200">
                              <circle cx="160" cy="100" r="45" fill="#ccc"/>
                              <rect x="220" y="72" width="90" height="12" rx="6" fill="#ccc"/>
                              <rect x="220" y="94" width="60" height="8" rx="4" fill="#ddd"/>
                              <rect x="220" y="110" width="75" height="8" rx="4" fill="#ddd"/>
                            </svg>
                            {% endif %}
                        </div>
                        <div class="partner-info">
                            <p class="partner-name">{{ sponsor.name }}</p>
                            <span class="partner-badge partner-badge-{{ sponsor.tier }}">{{ sponsor.tier }}</span>
                        </div>
                    </div>
                </a>
                {% endfor %}
            </div>
        </div>
    </div>
    {% endif %}
</div>
