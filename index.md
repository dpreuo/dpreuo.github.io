---
layout: default
---

<style>
  .pub {
    display: grid;
    grid-template-columns: 160px 1fr;
    gap: 1.2em;
    align-items: start;
    margin-bottom: 1.5em;
    padding: 1em;
    background: rgba(255, 255, 255, 0.4); /* keeps text readable over the background */
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

## About Me

<img class="profile-picture" src="images/headshot.jpg">

I am a theoretical physicist, currently working as a postdoc in the group of [Adolfo Grushin](https://www.ikerbasque.net/en/adolfo-g-grushin) at the Donostia International Physics Center in San Sebastian / Donostia.




## Research Interests

Most of my work centers on understanding how topological and symmetry-protected phases of matter can be understood without relying on momentum space. I have worked a lot on non-interacting topological systems such as Chern insulators, spin Hall, with crystal-symmetric materials. More recently I am focussing mostly on interacting phases such as magnetic matter, fractional Hall phases and quantum spin liquids. 

### Some links:

[Google scholar](https://scholar.google.com/citations?user=RcwugQMAAAAJ&hl=en) / [Github](https://github.com/dpreuo) / [arXiv](https://arxiv.org/search/?searchtype=author&query=d%27Ornellas%2C+P) / [Orcid](https://orcid.org/0000-0002-2349-0044)

## Recent Works

<div class="pubs">
{%- for pub in site.data.publications limit: 4 %}
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


This website is based on the [researcher](https://github.com/ankitsultana/researcher) template by Ankit Sultana.