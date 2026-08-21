---
layout: default-full
title: "Social Programme"
header_type: "ida"
ida-header: true
---

<main class="container-lg pb-3 flex-fill">
    <div class="row pt-4">
        <div class="col-12">
            <h1 class="mb-4">Social Programme</h1>
            <p class="lead mb-4">IDA 2027 offers a rich social programme to help participants connect and enjoy the host city.</p>
        </div>
    </div>

    <div class="row">
        {% for event in site.data.social_programme %}
        <div class="col-md-6 col-lg-4 mb-4">
            <div class="card h-100" style="border-top: 4px solid #07286E;">
                <div class="card-body">
                    <h5 class="card-title">{{ event.title }}</h5>
                    <p class="card-text">
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
        </div>
        {% endfor %}
    </div>
</main>
