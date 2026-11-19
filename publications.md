---
layout: default
title: Publications
---
<style>
  .pub {
    display: grid;
    grid-template-columns: 160px 1fr;
    gap: 1.2em;
    align-items: start;
    margin-bottom: 1.5em;
    padding: 1em;
    background: rgba(255, 255, 255, 0.75); /* keeps text readable over the background */
    border-radius: 6px;
  }
  .pub-image img,
  .pub-image .pub-noimage {
    width: 100%;
    border-radius: 4px;
  }
  .pub-image .pub-noimage {
    aspect-ratio: 4 / 3;
    background: rgba(61, 90, 128, 0.08);
  }
  .pub-title { margin: 0 0 0.3em; font-weight: bold; }
  .pub-meta { margin: 0 0 0.6em; font-size: 0.9em; }
  .pub-blurb p { margin: 0; }
  /* on narrow screens, put the image above the text */
  @media (max-width: 600px) {
    .pub { grid-template-columns: 1fr; }
    .pub-image { max-width: 240px; }
  }
</style>
## Publications

<div class="pubs">
{%- for pub in site.data.publications %}
<div class="pub">
<div class="pub-image">
{%- if pub.image %}
<img src="{{ pub.image }}" alt="Figure from {{ pub.title | strip_html }}">
{%- else %}
<div class="pub-noimage"></div>
{%- endif %}
</div>
<div class="pub-text">
<p class="pub-title"><a href="{{ pub.link }}">{{ pub.title }}</a></p>
<p class="pub-meta">{{ pub.authors }}<br><em>{{ pub.journal }}</em> ({{ pub.year }})</p>
<div class="pub-blurb">{{ pub.blurb | markdownify }}</div>
</div>
</div>
{%- endfor %}
</div>
