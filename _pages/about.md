---
permalink: /
lang: en
seo_title: "Keito Kozaki (神崎恵土)"
description: "Keito Kozaki (神崎恵土), master's student at the Media Dynamics Laboratory, Hokkaido University. Recommender systems, and interpreting model internals and datasets."
author_profile: false
redirect_from:
  - /about/
  - /about.html
---

{% include base_path %}

<!-- Intro: the portrait, name, affiliation and contact links.
     Everything here is read from the `author:` block in _config.yml, so edit
     that file rather than this markup. The sections below are rendered by the
     includes in _includes/home/, which read the files in _data/. -->

<div class="home-intro">
  <div class="home-intro__photo">
    <img src="{{ site.author.avatar | prepend: '/images/' | prepend: base_path }}" alt="{{ site.author.name }}" fetchpriority="high" />
  </div>
  <div class="home-intro__body">
    <h1 class="home-intro__name">{{ site.author.name }}</h1>
    {% if site.author.name_ja %}<p class="home-intro__alt-name" lang="ja">{{ site.author.name_ja }}</p>{% endif %}
    <p class="home-intro__affiliation">{{ site.author.employer }}</p>
    <ul class="home-intro__links">
      {% if site.author.email %}<li><a href="mailto:{{ site.author.email }}">Email</a></li>{% endif %}
      {% if site.author.googlescholar %}<li><a href="{{ site.author.googlescholar }}">Google Scholar</a></li>{% endif %}
      {% if site.author.orcid %}<li><a href="{{ site.author.orcid }}">ORCID</a></li>{% endif %}
      {% if site.author.github %}<li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>{% endif %}
      {% if site.author.twitter %}<li><a href="https://x.com/{{ site.author.twitter }}">X</a></li>{% endif %}
      {% if site.author.linkedin %}<li><a href="https://www.linkedin.com/in/{{ site.author.linkedin }}">LinkedIn</a></li>{% endif %}
      <li><a href="{{ base_path }}/cv/">CV</a></li>
    </ul>
  </div>
</div>

I am a first-year master's student at the Media Dynamics Laboratory, Graduate
School of Information Science and Technology, Hokkaido University. My research is on
recommender systems, and I am particularly interested in interpreting what
happens inside the models and what the benchmark datasets actually measure.
More recently I have also become interested in digital twins that imitate
people.

<div class="home-section" id="news">
  <h2 class="home-section__title">News<span class="home-section__hint">scroll &darr;</span></h2>
  {% include home/news-feed.html %}
</div>

<div class="home-section" id="publications">
  <h2 class="home-section__title">Publications</h2>
  {% include home/publication-list.html more=true %}
</div>

<div class="home-section" id="media">
  <h2 class="home-section__title">Media Coverage</h2>
  {% include home/media-list.html %}
</div>

<div class="home-section" id="awards">
  <h2 class="home-section__title">Awards</h2>
  {% include home/award-list.html %}
</div>

<div class="home-section" id="scholarships">
  <h2 class="home-section__title">Scholarships and Fellowships</h2>
  {% include home/grant-list.html %}
</div>

<div class="home-section" id="education">
  <h2 class="home-section__title">Education</h2>
  {% include home/entry-list.html entries=site.data.education %}
</div>

<div class="home-section" id="experience">
  <h2 class="home-section__title">Experience</h2>
  {% include home/entry-list.html entries=site.data.experience %}
</div>
