---
permalink: /
author_profile: false
redirect_from:
  - /about/
  - /about.html
---

{% include base_path %}

<!-- Intro: the portrait, name, affiliation and contact links.
     Everything here is read from the `author:` block in _config.yml, so edit
     that file rather than this markup. -->

<div class="home-intro">
  <div class="home-intro__photo">
    <img src="{{ site.author.avatar | prepend: '/images/' | prepend: base_path }}" alt="{{ site.author.name }}" fetchpriority="high" />
  </div>
  <div class="home-intro__body">
    <h1 class="home-intro__name">{{ site.author.name }}</h1>
    <p class="home-intro__affiliation">{{ site.author.employer }}</p>
    <ul class="home-intro__links">
      {% if site.author.email %}<li><a href="mailto:{{ site.author.email }}">Email</a></li>{% endif %}
      {% if site.author.googlescholar %}<li><a href="{{ site.author.googlescholar }}">Google Scholar</a></li>{% endif %}
      {% if site.author.github %}<li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>{% endif %}
      {% if site.author.orcid %}<li><a href="{{ site.author.orcid }}">ORCID</a></li>{% endif %}
      {% if site.author.twitter %}<li><a href="https://x.com/{{ site.author.twitter }}">X</a></li>{% endif %}
      <li><a href="{{ base_path }}/cv/">CV</a></li>
    </ul>
  </div>
</div>

TODO: write a short self-introduction here, two or three sentences.
Something along the lines of: what you are working on now, which research
area it belongs to, and what you are interested in more broadly. This is the
first thing a reader sees, so keep it plain and specific.

<div class="home-section" id="news">
  <h2 class="home-section__title">News<span class="home-section__hint">scroll &darr;</span></h2>
  <div class="news-feed">
    {%- assign news_items = site.data.news | sort: 'date' | reverse -%}
    {%- for item in news_items %}
    <div class="news-feed__item">
      <div class="news-feed__date">{{ item.date | date: "%Y.%m" }}</div>
      <div class="news-feed__body">{{ item.en | markdownify | remove: '<p>' | remove: '</p>' }}</div>
    </div>
    {%- endfor %}
  </div>
</div>

<div class="home-section" id="publications">
  <h2 class="home-section__title">Publications</h2>
  {%- assign publications = site.publications | sort: 'date' | reverse -%}
  {%- if publications.size == 0 %}
  <p>TODO: add one Markdown file per paper under <code>_publications/</code> and it
  will appear here as well as on the <a href="{{ base_path }}/publications/">Publications</a> page.</p>
  {%- else %}
  <ol class="pub-list">
    {%- for publication in publications %}
    <li>
      <span class="pub-list__title">{{ publication.title }}</span>
      {%- if publication.award %}<span class="pub-list__award">{{ publication.award }}</span>{% endif %}
      <span class="pub-list__venue">{{ publication.venue }}{% if publication.date %}, {{ publication.date | date: "%Y" }}{% endif %}</span>
      <span class="pub-list__links">
        <a href="{{ publication.url | prepend: base_path }}">details</a>
        {%- if publication.paperurl %}<a href="{{ publication.paperurl }}">paper</a>{% endif %}
        {%- if publication.codeurl %}<a href="{{ publication.codeurl }}">code</a>{% endif %}
        {%- if publication.slidesurl %}<a href="{{ publication.slidesurl }}">slides</a>{% endif %}
        {%- if publication.bibtexurl %}<a href="{{ publication.bibtexurl }}">bibtex</a>{% endif %}
      </span>
    </li>
    {%- endfor %}
  </ol>
  {%- endif %}
</div>

<div class="home-section" id="experience">
  <h2 class="home-section__title">Experience</h2>
  <ul class="exp-list">
    {%- for entry in site.data.experience %}
    <li class="exp-list__item">
      <div class="exp-list__period">{{ entry.period }}</div>
      <div class="exp-list__body">
        <div>{{ entry.role_en }}</div>
        <div class="exp-list__org">
          {%- if entry.url %}<a href="{{ entry.url }}">{{ entry.org_en }}</a>{% else %}{{ entry.org_en }}{% endif %}
        </div>
      </div>
    </li>
    {%- endfor %}
  </ul>
</div>
