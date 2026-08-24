---
permalink: /ja/
lang: ja
seo_title: "神崎恵土 (Keito Kozaki)"
description: "神崎恵土 (Keito Kozaki)。北海道大学 メディアダイナミクス研究室 修士課程。推薦システム、特にモデル内部やデータセットの解釈に取り組んでいます。"
author_profile: false
---

{% include base_path %}

<!-- Japanese version of the front page. It renders the same includes as
     _pages/about.md with lang="ja", so news, awards, education and experience
     only have to be written once, in the files under _data/. -->

<div class="home-intro">
  <div class="home-intro__photo">
    <img src="{{ site.author.avatar | prepend: '/images/' | prepend: base_path }}" alt="{{ site.author.name_ja | default: site.author.name }}" fetchpriority="high" />
  </div>
  <div class="home-intro__body">
    <h1 class="home-intro__name">{{ site.author.name_ja | default: site.author.name }}</h1>
    <p class="home-intro__alt-name" lang="en">{{ site.author.name }}</p>
    <p class="home-intro__affiliation">{{ site.author.employer_ja | default: site.author.employer }}</p>
    <ul class="home-intro__links">
      {% if site.author.email %}<li><a href="mailto:{{ site.author.email }}">メール</a></li>{% endif %}
      {% if site.author.googlescholar %}<li><a href="{{ site.author.googlescholar }}">Google Scholar</a></li>{% endif %}
      {% if site.author.orcid %}<li><a href="{{ site.author.orcid }}">ORCID</a></li>{% endif %}
      {% if site.author.github %}<li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>{% endif %}
      {% if site.author.twitter %}<li><a href="https://x.com/{{ site.author.twitter }}">X</a></li>{% endif %}
      {% if site.author.linkedin %}<li><a href="https://www.linkedin.com/in/{{ site.author.linkedin }}">LinkedIn</a></li>{% endif %}
      <li><a href="{{ base_path }}/cv/">CV</a></li>
      <li><a href="{{ base_path }}/">English</a></li>
    </ul>
  </div>
</div>

北海道大学 大学院情報科学院 メディアダイナミクス研究室の修士1年です。
推薦システム、特にモデル内部やデータセットの解釈に興味があります。
また近年は人を模倣したデジタルツインの研究にも興味があります。

<div class="home-section" id="news">
  <h2 class="home-section__title">お知らせ<span class="home-section__hint">scroll &darr;</span></h2>
  {% include home/news-feed.html lang="ja" %}
</div>

<div class="home-section" id="publications">
  <h2 class="home-section__title">業績</h2>
  {% include home/publication-list.html lang="ja" domestic=true %}
</div>

<div class="home-section" id="media">
  <h2 class="home-section__title">紹介記事</h2>
  {% include home/media-list.html lang="ja" %}
</div>

<div class="home-section" id="awards">
  <h2 class="home-section__title">受賞</h2>
  {% include home/award-list.html lang="ja" %}
</div>

<div class="home-section" id="scholarships">
  <h2 class="home-section__title">奨学金</h2>
  {% include home/grant-list.html lang="ja" %}
</div>

<div class="home-section" id="education">
  <h2 class="home-section__title">学歴</h2>
  {% include home/entry-list.html entries=site.data.education lang="ja" %}
</div>

<div class="home-section" id="experience">
  <h2 class="home-section__title">経歴</h2>
  {% include home/entry-list.html entries=site.data.experience lang="ja" %}
</div>
