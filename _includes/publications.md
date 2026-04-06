<h2 id="publications" style="margin: 2px 0px 10px;">Publications</h2>

<div class="publications">

{% assign pubs = site.data.publications.main | sort: "year" | reverse %}
{% assign years = pubs | map: "year" | uniq %}

{% for year in years %}
  <h3 style="margin-top: 28px; margin-bottom: 12px; font-size: 1.6rem; font-weight: 700; color: #222;">
    {{ year }}
  </h3>

  <ol class="bibliography" style="margin-top: 0;">
    {% for link in pubs %}
      {% if link.year == year %}
      <li style="margin-bottom: 16px;">
        <div class="pub-row" style="display: block;">

          <div class="title" style="font-weight: 600; margin-bottom: 4px;">
            {% if link.pdf %}
              <a href="{{ link.pdf }}" target="_blank">{{ link.title }}</a>
            {% else %}
              {{ link.title }}
            {% endif %}
          </div>

          <div class="author" style="margin-bottom: 4px;">
            {{ link.authors }}
          </div>

          <div class="periodical" style="margin-bottom: 6px;">
            <em>{{ link.conference }}</em>
          </div>

          <div class="links">
            {% if link.conference_short %}
              <span class="pub-badge">{{ link.conference_short }}</span>
            {% endif %}

            {% if link.pdf %}
              <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
            {% endif %}
            {% if link.code %}
              <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
            {% endif %}
            {% if link.page %}
              <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
            {% endif %}
            {% if link.bibtex %}
              <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
            {% endif %}
            {% if link.notes %}
              <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
            {% endif %}
            {% if link.others %}
              {{ link.others }}
            {% endif %}
          </div>

        </div>
      </li>
      {% endif %}
    {% endfor %}
  </ol>
{% endfor %}

</div>
