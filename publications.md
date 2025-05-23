---
layout: default
title: Publications
permalink: /publications/
---

# Publications

{% if site.data.publications and site.data.publications.size > 0 %}
  {% for publication in site.data.publications %}
  <div class="publication-item">
    <h3>{{ publication.title | escape }}</h3>
    <p><em>{{ publication.authors | escape }}</em></p>
    <p>
      {{ publication.journal | escape }}
      {% if publication.volume %}, Vol. {{ publication.volume | escape }}{% endif %}
      {% if publication.number %}, No. {{ publication.number | escape }}{% endif %}
      {% if publication.pages %}, pp. {{ publication.pages | escape }}{% endif %}
      ({{ publication.year | escape }})
    </p>
    <p>
      {% if publication.doi %}<a href="https://doi.org/{{ publication.doi | escape }}" target="_blank" rel="noopener noreferrer">DOI: {{ publication.doi | escape }}</a>{% endif %}
      {% if publication.url and publication.doi %} | {% endif %}
      {% if publication.url %}<a href="{{ publication.url | escape }}" target="_blank" rel="noopener noreferrer">Link</a>{% endif %}
    </p>
    {% if publication.abstract %}
      <details>
        <summary><strong>Abstract</strong> (click to expand)</summary>
        <p>{{ publication.abstract | escape | nl2br }}</p>
      </details>
    {% endif %}
  </div>
  <hr>
  {% endfor %}
{% else %}
  <p>No publications yet. This section will be updated soon.</p>
{% endif %}
