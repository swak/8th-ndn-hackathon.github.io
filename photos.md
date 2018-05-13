---
layout: page
title: Photos
---
{% for image in site.static_files %}
    {% if image.path contains '_assets/pics' %}
        <img src="{{ site.baseurl }}{{ image.path }}" alt="image" />
    {% endif %}
{% endfor %}
