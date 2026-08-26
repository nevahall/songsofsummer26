---
layout: default
title: Home
---

<section class="hero">
  <p class="eyebrow">The annual playlist guide</p>
  <h1>Top 10 songs of the summer</h1>
  <p class="hero__intro">Welcome to the countdown. Use this space to introduce your project, explain your criteria, and set the mood for the season.</p>
  <a class="button" href="#countdown">Explore the countdown <span aria-hidden="true">↓</span></a>
</section>

<section class="section-heading" id="countdown">
  <div>
    <p class="eyebrow">The countdown</p>
    <h2>Ten tracks. One unforgettable summer.</h2>
  </div>
  <p class="section-heading__note">Replace the placeholder Markdown in each song page with your own review.</p>
</section>

<div class="song-grid">
  {% assign songs = site.songs | sort: "rank" %}
  {% for song in songs %}
    <a class="song-card" href="{{ song.url | relative_url }}">
      <span class="song-card__rank">{{ song.rank | prepend: "0" | slice: -2, 2 }}</span>
      <span class="song-card__art song-card__art--{{ song.rank }}" aria-hidden="true"><span>♪</span></span>
      <span class="song-card__details">
        <strong>{{ song.title }}</strong>
        <span>{{ song.performer }}</span>
      </span>
      <span class="song-card__arrow" aria-hidden="true">↗</span>
    </a>
  {% endfor %}
</div>
