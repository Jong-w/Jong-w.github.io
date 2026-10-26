<style>
/* Isolated publication layout for the official Minimal Light theme. */
#publications + .jk-publications { width: 100%; }
.jk-publications, .jk-publications * { box-sizing: border-box !important; }
.jk-publications .jk-paper {
  display: grid !important;
  grid-template-columns: minmax(0, 34%) minmax(0, 1fr) !important;
  align-items: start !important;
  column-gap: 22px !important;
  width: 100% !important;
  min-height: 0 !important;
  margin: 0 0 24px !important;
  padding: 0 0 24px !important;
  border-bottom: 1px solid #e6e6e6;
  clear: both !important;
  float: none !important;
}
.jk-publications .jk-paper:last-child { border-bottom: 0; }
.jk-publications figure.jk-figure {
  display: block !important;
  position: relative !important;
  float: none !important;
  width: 100% !important;
  max-width: 100% !important;
  height: 160px !important;
  min-height: 0 !important;
  margin: 0 !important;
  padding: 0 !important;
  overflow: hidden !important;
  border: 1px solid #ececec;
  border-radius: 4px;
  background: #fff;
}
.jk-publications figure.jk-figure > img {
  display: block !important;
  float: none !important;
  position: static !important;
  width: 100% !important;
  max-width: 100% !important;
  height: 100% !important;
  max-height: 100% !important;
  margin: 0 !important;
  padding: 0 !important;
  object-fit: contain !important;
  object-position: center !important;
  border: 0 !important;
  box-shadow: none !important;
}
.jk-publications .jk-tag {
  position: absolute !important;
  top: 6px; left: 6px; z-index: 1;
  padding: 3px 7px;
  color: #fff; background: #083a70;
  font-size: 10px; font-weight: 600; line-height: 1.2;
  border-radius: 2px;
}
.jk-publications .jk-info { min-width: 0; overflow-wrap: anywhere; }
.jk-publications .jk-title { font-size: 15px; font-weight: 700; line-height: 1.45; margin: 0 0 5px; }
.jk-publications .jk-authors { line-height: 1.5; margin: 0 0 4px; }
.jk-publications .jk-venue { font-style: italic; line-height: 1.5; margin: 0 0 8px; }
.jk-publications .jk-links { display: flex; flex-wrap: wrap; gap: 6px; align-items: center; }
.jk-publications .jk-links a { display: inline-block; padding: 3px 9px; border: 1px solid #b9c2ca; border-radius: 3px; font-size: 12px; line-height: 1.5; text-decoration: none; }
.jk-publications .jk-award { color: #c93e30; font-size: 12px; font-style: italic; font-weight: 600; }
@media (max-width: 620px) {
  .jk-publications .jk-paper { grid-template-columns: minmax(0, 32%) minmax(0, 1fr) !important; column-gap: 12px !important; }
  .jk-publications figure.jk-figure { height: 115px !important; }
  .jk-publications .jk-title { font-size: 14px; }
}
@media (max-width: 430px) {
  .jk-publications .jk-paper { grid-template-columns: minmax(0, 1fr) !important; row-gap: 12px !important; }
  .jk-publications figure.jk-figure { width: min(100%, 260px) !important; height: 155px !important; }
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
