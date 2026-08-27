---
layout: archive
title: "CV"
permalink: /ja/cv/
lang: ja
alternate_en: /cv/
alternate_ja: /ja/cv/
author_profile: false
---

{% include base_path %}

<!-- Japanese counterpart of _pages/cv.md. It renders the same includes with
     lang="ja", so both pages are driven by the same files in _data/ and the
     _publications collection and cannot drift apart.

     This exists so that a reader who switched to Japanese and then opened the
     CV is not dropped back into the English site. -->

<div class="home-section" id="education">
  <h2 class="home-section__title">学歴</h2>
  {% include home/entry-list.html entries=site.data.education lang="ja" %}
</div>

<div class="home-section" id="experience">
  <h2 class="home-section__title">経歴</h2>
  {% include home/entry-list.html entries=site.data.experience lang="ja" %}
</div>

<div class="home-section" id="awards">
  <h2 class="home-section__title">受賞</h2>
  {% include home/award-list.html lang="ja" %}
</div>

<div class="home-section" id="scholarships">
  <h2 class="home-section__title">奨学金</h2>
  {% include home/grant-list.html lang="ja" %}
</div>

<div class="home-section" id="publications">
  <h2 class="home-section__title">業績</h2>
  {% include home/publication-list.html lang="ja" domestic=true %}
</div>
