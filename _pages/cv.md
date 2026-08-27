---
layout: archive
title: "CV"
permalink: /cv/
lang: en
alternate_en: /cv/
alternate_ja: /ja/cv/
author_profile: false
redirect_from:
  - /resume
---

{% include base_path %}

<!-- Every section below is rendered from the files in _data/ and the
     _publications collection, the same sources the front page uses, so the CV
     never falls out of step with it. Sections that only belong on the CV, such
     as scholarships, read their own data file. -->

<div class="home-section" id="education">
  <h2 class="home-section__title">Education</h2>
  {% include home/entry-list.html entries=site.data.education %}
</div>

<div class="home-section" id="experience">
  <h2 class="home-section__title">Experience</h2>
  {% include home/entry-list.html entries=site.data.experience %}
</div>

<div class="home-section" id="awards">
  <h2 class="home-section__title">Awards</h2>
  {% include home/award-list.html %}
</div>

<div class="home-section" id="scholarships">
  <h2 class="home-section__title">Scholarships and Fellowships</h2>
  {% include home/grant-list.html %}
</div>

<div class="home-section" id="publications">
  <h2 class="home-section__title">Publications</h2>
  {% include home/publication-list.html domestic=true %}
</div>
