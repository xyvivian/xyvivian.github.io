---
layout: default
title: Experience
permalink: /experience/
nav_key: experience
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
        <h2 class="lead-title">Experience</h2>
        <div class="section-copy">
          <p>
            My recent work combines academic research with industry collaborations
            across large-scale retrieval, anomaly detection, and financial
            time-series modeling.
          </p>
        </div>
      </section>

      <section class="list-section">
        <div class="timeline-list">
          {% for item in site.data.experience %}
            <article class="timeline-item">
              <div class="timeline-header">
                <div class="timeline-role">{{ item.title }}, {{ item.organization }}</div>
                <div class="timeline-meta">{{ item.period }}</div>
              </div>
              <div class="timeline-location">{{ item.location }}</div>
              <div class="timeline-summary">{{ item.summary }}</div>
              <ul class="timeline-bullets">
                {% for bullet in item.bullets %}
                  <li>{{ bullet }}</li>
                {% endfor %}
              </ul>
            </article>
          {% endfor %}
        </div>
      </section>
    </div>
  </main>
</div>
