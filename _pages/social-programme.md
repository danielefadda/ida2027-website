---
layout: default-full
title: "Social Programme"
header_type: "conference"
header_white: true
header_title: "{{ site.conference.acronym }} Social Programme"
conference-header: true
---

<main class="container-lg pb-3 flex-fill">
    <div class="row pt-4">
        <div class="col-12">
            <h1 class="mb-4">Social Programme</h1>
            <p class="lead mb-4">{{ site.conference.acronym }} offers a rich social programme to help participants connect and enjoy the host city.</p>
        </div>
    </div>

    <div class="row">
        {% for event in site.data.social_programme %}
        <div class="col-12 mb-4">
            <div class="card social-card rounded-0" style="border-left: 4px solid #000;">
                <div class="row no-gutters">
                    <div class="col-md-4 d-flex align-items-center">
                        <div class="card-body">
                            <h4 class="card-title mb-3">{{ event.title }}</h4>
                            <p class="card-text mb-2">
                                <strong><i class="fas fa-calendar-alt"></i> {{ event.date }}</strong><br>
                                <i class="fas fa-clock"></i> {{ event.time }}<br>
                                <i class="fas fa-map-marker-alt"></i> {{ event.venue }}
                            </p>
                            <p class="card-text">{{ event.description }}</p>
                            {% if event.bus_info %}
                            <p class="card-text"><small class="text-muted"><i class="fas fa-bus"></i> {{ event.bus_info }}</small></p>
                            {% endif %}
                        </div>
                    </div>
                    <div class="col-md-8">
                        <img src="{{ event.image | relative_url }}" class="card-img-right" alt="{{ event.title }}" onerror="this.onerror=null;this.src='https://picsum.photos/800/250?blur';">
                    </div>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</main>
