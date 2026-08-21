---
layout: default-full
title: "IDA 2027"
header_title: "IDA 2027"
subtitle: "25th International Symposium on Intelligent Data Analysis"
header_type: hero
header_img: /assets/images/ida2027-hero.jpg
project_links:
    - url: https://github.com/XXX # url1
      icon: fab fa-github         # Fontawesome icon code1
      label: View on Github       # Label on button 1
    - url: https://colab.research.google.com/XXX #url2
      icon: fab fa-python   # Fontawesome icon code2
      label: Open in Colab  # Label on button 2
---

<div class="container-lg mt-4">
    <div class="home-header text-center mb-5">
        <div class="row">
            <div class="col-lg-12 text-center mb-5">
                <h1 style="font-size: 3rem; font-weight: 700;">IDA 2027</h1>
                <h2 style="font-weight: 400;">25th International Symposium on Intelligent Data Analysis</h2>
                <p class="lead mt-3">
                    <strong>April 22-24, 2027</strong> &mdash; Location TBD
                </p>
                <div class="mt-4">
                    <a href="{{ '/registration/' | relative_url }}" class="btn btn-primary btn-lg me-3">Register Now</a>
                    <a href="{{ '/regular-paper-track/' | relative_url }}" class="btn btn-outline-primary btn-lg">Submit a Paper</a>
                </div>
            </div>
        </div>
    </div>
    <!-- <div class="row mb-5">
        <div class="col-lg-12">
            <h3 class="mb-4">Key Dates</h3>
            <div class="badge-container">
                {% for key in site.data.dates %}
                <div class="card stat-card" style="min-width: 180px;">
                    <div class="card-body">
                        <div class="stat-value accent-secondary">{{ key[1].display }}</div>
                        <div class="stat-label">{{ key[1].label }}</div>
                    </div>
                </div>
                {% endfor %}
            </div>
        </div>
    </div> -->
    <div class="row mb-5">
        <div class="col-6">
            <h3>Symposium on Intelligent Data Analysis 2027</h3>
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
                        <th>Key Date</th>
                        <th>Event</th>
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
                            <img src="{{ sponsor.logo | relative_url }}" alt="{{ sponsor.name }}" class="partner-logo">
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
