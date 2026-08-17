---
permalink: /ja/
author_profile: false
---

{% include base_path %}

<!-- Japanese version of the front page. It reads the same data files as
     _pages/about.md but uses their `ja` fields, so news and experience only
     have to be written once. -->

<div class="home-intro">
  <div class="home-intro__photo">
    <img src="{{ site.author.avatar | prepend: '/images/' | prepend: base_path }}" alt="{{ site.author.name_ja | default: site.author.name }}" fetchpriority="high" />
  </div>
  <div class="home-intro__body">
    <h1 class="home-intro__name">{{ site.author.name_ja | default: site.author.name }}</h1>
    <p class="home-intro__affiliation">{{ site.author.employer_ja | default: site.author.employer }}</p>
    <ul class="home-intro__links">
      {% if site.author.email %}<li><a href="mailto:{{ site.author.email }}">メール</a></li>{% endif %}
      {% if site.author.googlescholar %}<li><a href="{{ site.author.googlescholar }}">Google Scholar</a></li>{% endif %}
      {% if site.author.github %}<li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>{% endif %}
      {% if site.author.orcid %}<li><a href="{{ site.author.orcid }}">ORCID</a></li>{% endif %}
      {% if site.author.twitter %}<li><a href="https://x.com/{{ site.author.twitter }}">X</a></li>{% endif %}
      <li><a href="{{ base_path }}/cv/">CV</a></li>
      <li><a href="{{ base_path }}/">English</a></li>
    </ul>
  </div>
</div>

TODO: 自己紹介を2〜3文で書いてください。英語版と同じ内容の日本語訳で構いません。

<div class="home-section" id="news">
  <h2 class="home-section__title">お知らせ<span class="home-section__hint">scroll &darr;</span></h2>
  <div class="news-feed">
    {%- assign news_items = site.data.news | sort: 'date' | reverse -%}
    {%- for item in news_items %}
    <div class="news-feed__item">
      <div class="news-feed__date">{{ item.date | date: "%Y.%m" }}</div>
      <div class="news-feed__body">{{ item.ja | default: item.en | markdownify | remove: '<p>' | remove: '</p>' }}</div>
    </div>
    {%- endfor %}
  </div>
</div>

<div class="home-section" id="publications">
  <h2 class="home-section__title">業績</h2>
  {%- assign publications = site.publications | sort: 'date' | reverse -%}
  {%- if publications.size == 0 %}
  <p>TODO: <code>_publications/</code> に論文ごとの Markdown ファイルを追加すると、ここと
  <a href="{{ base_path }}/publications/">Publications</a> ページの両方に表示されます。</p>
  {%- else %}
  <ol class="pub-list">
    {%- for publication in publications %}
    <li>
      <span class="pub-list__title">{{ publication.title }}</span>
      {%- if publication.award %}<span class="pub-list__award">{{ publication.award }}</span>{% endif %}
      <span class="pub-list__venue">{{ publication.venue }}{% if publication.date %}, {{ publication.date | date: "%Y" }}{% endif %}</span>
      <span class="pub-list__links">
        <a href="{{ publication.url | prepend: base_path }}">詳細</a>
        {%- if publication.paperurl %}<a href="{{ publication.paperurl }}">論文</a>{% endif %}
        {%- if publication.codeurl %}<a href="{{ publication.codeurl }}">コード</a>{% endif %}
        {%- if publication.slidesurl %}<a href="{{ publication.slidesurl }}">スライド</a>{% endif %}
        {%- if publication.bibtexurl %}<a href="{{ publication.bibtexurl }}">bibtex</a>{% endif %}
      </span>
    </li>
    {%- endfor %}
  </ol>
  {%- endif %}
</div>

<div class="home-section" id="experience">
  <h2 class="home-section__title">経歴</h2>
  <ul class="exp-list">
    {%- for entry in site.data.experience %}
    <li class="exp-list__item">
      <div class="exp-list__period">{{ entry.period }}</div>
      <div class="exp-list__body">
        <div>{{ entry.role_ja | default: entry.role_en }}</div>
        <div class="exp-list__org">
          {%- assign org = entry.org_ja | default: entry.org_en -%}
          {%- if entry.url %}<a href="{{ entry.url }}">{{ org }}</a>{% else %}{{ org }}{% endif %}
        </div>
      </div>
    </li>
    {%- endfor %}
  </ul>
</div>
