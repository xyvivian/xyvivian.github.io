---
layout: default
title: Research
permalink: /research/
nav_key: research
---
{% assign profile = site.data.profile %}

<div class="page-shell">
  <main class="content-layout">
    <aside class="sidebar">
      <img class="profile-photo" src="{{ profile.photo | relative_url }}" alt="Portrait of {{ profile.name }}">
      <h1 class="profile-name">{{ profile.name }}</h1>
      <div class="profile-title">{{ profile.title }}</div>
      <div class="profile-affiliation">{{ profile.affiliation }}</div>
      <ul class="profile-links">
        <li><a class="icon-link" href="mailto:{{ profile.email }}"><img src="{{ '/assets/icons/email.svg' | relative_url }}" alt=""><span>Email</span></a></li>
        <li><a class="icon-link" href="{{ profile.resume_file | relative_url }}"><img src="{{ '/assets/icons/cv.svg' | relative_url }}" alt=""><span>{{ profile.resume_label }}</span></a></li>
        <li><a class="icon-link" href="{{ profile.github }}"><img src="{{ '/assets/icons/github.svg' | relative_url }}" alt=""><span>GitHub</span></a></li>
        <li><a class="icon-link" href="{{ profile.linkedin }}"><img src="{{ '/assets/icons/linkedin.svg' | relative_url }}" alt=""><span>LinkedIn</span></a></li>
      </ul>
    </aside>

    <div class="content-column">
      <section>
        <h2 class="lead-title">Research</h2>
        <div class="section-copy">
          <p>
            I work on machine learning systems that are robust, efficient, and
            useful across structured and unstructured data. Current interests
            include foundation models, retrieval, evaluation, and outlier detection.
          </p>
        </div>
      </section>

      <section class="list-section">
        <h2 class="section-title">Publications</h2>
        {% for group in site.data.publications %}
          <div class="pub-group">
            <h3>{{ group.category }}</h3>
            <div class="pub-list">
              {% for pub in group.entries %}
                <article class="pub-item">
                  <div class="pub-year">{{ pub.year }}</div>
                  <div>
                    <h4 class="pub-title">{{ pub.title }}</h4>
                    <div class="pub-authors">{{ pub.authors }}</div>
                    <div class="pub-venue">{{ pub.venue }}</div>
                    {% if pub.note != "" %}
                      <div class="pub-note">{{ pub.note }}</div>
                    {% endif %}
                  </div>
                </article>
              {% endfor %}
            </div>
          </div>
        {% endfor %}
      </section>
    </div>
  </main>
</div>
