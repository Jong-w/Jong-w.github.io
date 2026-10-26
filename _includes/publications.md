<style>
/* Publication layout overrides only; the official Minimal Light theme remains active. */
.jk-publications, .jk-publications * { box-sizing: border-box; }
.jk-publications { margin-top: 18px; }
.jk-publications .jk-paper { display: flex; align-items: flex-start; gap: 22px; margin: 0 0 27px; padding: 0 0 24px; border-bottom: 1px solid #e9e9e9; width: 100%; clear: both; }
.jk-publications .jk-paper:last-child { border-bottom: 0; }
.jk-publications .jk-figure { position: relative; flex: 0 0 35%; width: 35%; min-width: 0; margin: 0; }
.jk-publications .jk-figure img { display: block; width: 100%; height: 155px; max-width: 100%; object-fit: contain; object-position: center; background: #fff; border: 1px solid #ececec; border-radius: 4px; }
.jk-publications .jk-tag { position: absolute; top: 7px; left: 7px; padding: 3px 7px; font-size: 10px; line-height: 1.2; font-weight: 600; color: #fff; background: #083a70; border-radius: 2px; }
.jk-publications .jk-info { flex: 1 1 0; min-width: 0; overflow-wrap: anywhere; }
.jk-publications .jk-title { font-size: 15px; font-weight: 700; line-height: 1.4; margin-bottom: 5px; }
.jk-publications .jk-authors { line-height: 1.5; margin-bottom: 4px; }
.jk-publications .jk-venue { font-style: italic; line-height: 1.5; margin-bottom: 8px; }
.jk-publications .jk-links { display: flex; align-items: center; flex-wrap: wrap; gap: 6px; }
.jk-publications .jk-links a { display: inline-block; padding: 3px 9px; border: 1px solid #b9c2ca; border-radius: 3px; font-size: 12px; line-height: 1.5; text-decoration: none; }
.jk-publications .jk-award { color: #c93e30; font-size: 12px; font-style: italic; font-weight: 600; }
@media (max-width: 620px) {
  .jk-publications .jk-paper { gap: 12px; }
  .jk-publications .jk-figure { flex-basis: 32%; width: 32%; }
  .jk-publications .jk-figure img { height: 110px; }
  .jk-publications .jk-title { font-size: 14px; }
}
@media (max-width: 430px) {
  .jk-publications .jk-paper { display: block; }
  .jk-publications .jk-figure { width: 100%; max-width: 240px; margin-bottom: 12px; }
  .jk-publications .jk-figure img { height: 145px; }
}
</style>
<h2 id="publications">Publications</h2>
<div class="jk-publications">
{% for paper in site.data.publications.main %}
<article class="jk-paper">
  {% if paper.image %}
  <figure class="jk-figure">
    <img src="{{ paper.image | relative_url }}" alt="Figure for {{ paper.title | escape }}" loading="lazy">
    {% if paper.conference_short %}<span class="jk-tag">{{ paper.conference_short }}</span>{% endif %}
  </figure>
  {% endif %}
  <div class="jk-info">
    <div class="jk-title">{% if paper.pdf %}<a href="{{ paper.pdf | relative_url }}" target="_blank" rel="noopener noreferrer">{{ paper.title }}</a>{% elsif paper.page %}<a href="{{ paper.page }}" target="_blank" rel="noopener noreferrer">{{ paper.title }}</a>{% else %}{{ paper.title }}{% endif %}</div>
    <div class="jk-authors">{{ paper.authors }}</div>
    <div class="jk-venue">{{ paper.conference }}</div>
    <div class="jk-links">
      {% if paper.pdf %}<a href="{{ paper.pdf | relative_url }}" target="_blank" rel="noopener noreferrer">PDF</a>{% endif %}
      {% if paper.code %}<a href="{{ paper.code }}" target="_blank" rel="noopener noreferrer">Code</a>{% endif %}
      {% if paper.page %}<a href="{{ paper.page }}" target="_blank" rel="noopener noreferrer">Project Page</a>{% endif %}
      {% if paper.notes %}<span class="jk-award">{{ paper.notes }}</span>{% endif %}
    </div>
  </div>
</article>
{% endfor %}
</div>
