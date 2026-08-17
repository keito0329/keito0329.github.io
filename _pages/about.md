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
      {% if site.author.orcid %}<li><a href="{{ site.author.orcid }}">ORCID</a></li>{% endif %}
      {% if site.author.github %}<li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>{% endif %}
      {% if site.author.twitter %}<li><a href="https://x.com/{{ site.author.twitter }}">X</a></li>{% endif %}
      {% if site.author.linkedin %}<li><a href="https://www.linkedin.com/in/{{ site.author.linkedin }}">LinkedIn</a></li>{% endif %}
      <li><a href="{{ base_path }}/cv/">CV</a></li>
    </ul>
  </div>
</div>

I am a master's student at the Media Dynamics Laboratory, Graduate School of
Information Science and Technology, Hokkaido University. My research is on
recommender systems, and I am particularly interested in interpreting what
happens inside the models and what the benchmark datasets actually measure.
More recently I have also become interested in digital twins that imitate
people.

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

<!-- Publications: international conference and journal papers, newest first.
     Domestic conference papers are left to the full Publications page so this
     English list stays readable. -->

<div class="home-section" id="publications">
  <h2 class="home-section__title">Publications</h2>
  {%- assign publications = site.publications | where_exp: "item", "item.category != 'domestic'" | sort: 'date' | reverse -%}
  {%- if publications.size == 0 %}
  <p>Add one Markdown file per paper under <code>_publications/</code> and it will
  appear here as well as on the <a href="{{ base_path }}/publications/">Publications</a> page.</p>
  {%- else %}
  <ol class="pub-list">
    {%- for publication in publications %}
    <li>
      <span class="pub-list__title">{{ publication.title }}</span>
      {%- if publication.award %}<span class="pub-list__award">{{ publication.award }}</span>{% endif %}
      {%- if publication.authors %}<span class="pub-list__authors">{{ publication.authors | markdownify | remove: '<p>' | remove: '</p>' }}</span>{% endif %}
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
  <p class="pub-list__more"><a href="{{ base_path }}/publications/">Full list of publications, including domestic conferences &rarr;</a></p>
  {%- endif %}
</div>

<div class="home-section" id="awards">
  <h2 class="home-section__title">Awards</h2>
  <ul class="award-list">
    {%- assign awards = site.data.awards | sort: 'date' | reverse -%}
    {%- for award in awards %}
    <li class="award-list__item">
      <div class="award-list__date">{{ award.date | date: "%Y.%m" }}</div>
      <div class="award-list__body">{{ award.en }}</div>
    </li>
    {%- endfor %}
  </ul>
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
