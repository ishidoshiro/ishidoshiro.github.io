---
layout: page
permalink: /publications/
title: Publications
description: Journal articles and proceedings, listed newest first.
nav: true
nav_order: 3
---

{% assign citation_total = 0 %}
{% for paper in site.data.citations.papers %}
{% assign citation_total = citation_total | plus: paper[1].citations %}
{% endfor %}

<div class="publications-page">
  <section class="publication-overview" aria-label="Google Scholar citation summary">
    <div class="publication-metrics">
      <div class="publication-metric">
        <strong>{{ site.data.citations.papers | size }}</strong>
        <span>Scholar records</span>
      </div>
      <div class="publication-metric">
        <strong>{{ citation_total }}</strong>
        <span>Total citations</span>
      </div>
      <div class="publication-metric">
        <strong>{{ site.data.citations.metadata.last_updated | date: '%b %-d, %Y' }}</strong>
        <span>Last updated</span>
      </div>
    </div>
    <p>
      Citation counts are updated automatically from
      <a href="https://scholar.google.com/citations?user={{ site.data.socials.scholar_userid }}">Google Scholar</a>.
    </p>
  </section>

  <div class="publication-tools">
    <label for="bibsearch">Find a publication</label>
    {% include bib_search.liquid %}
    <nav class="publication-topics" aria-label="Filter publications by topic">
      <span>Topics</span>
      <a href="#">All</a>
      <a href="#lnv">LNV / 0νββ</a>
      <a href="#dark%20matter">Dark matter</a>
      <a href="#neutrino%20astrophysics">Neutrino astrophysics</a>
      <a href="#detector%20r%26d">Detector R&amp;D</a>
    </nav>
  </div>

  <div class="publications">
    {% bibliography %}
  </div>
</div>
