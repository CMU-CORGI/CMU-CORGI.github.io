{% assign projsize = include.pub.projects | size %}
{% unless projsize == 0 %}

{% capture authors %}
{% for author in include.pub.authors %}
    {% assign found = nil %}
    {% assign matches = site.people |
        where_exp: "person", "person.tag == author" %}
    {% assign nmatches = matches | size %}
    {% if nmatches > 0 %}
        [{{matches[0].name}}]({{matches[0].url}}),
    {% else %}
        {% assign collab = site.data.collaborators[author] %}
        {% if collab %}
            {{collab.name}},
        {% else %}
            {{author}},
        {% endif %}
    {% endif %}
{% endfor %}
{% endcapture %}

{% assign authors = authors | strip_newlines | strip %}
{% assign authorsSize = authors | size | minus: 1 %}
{% assign authors = authors | slice: 0, authorsSize %}

{% capture projs %}
{% for proj in include.pub.projects %}
    {% assign matches = site.projects |
        where_exp: "other", "proj == other.tag" %}
    {% for match in matches %}
        [{{match.title}}]({{match.url}})
    {% endfor %}
{% endfor %}
{% endcapture %}

<h3 class="tight-h3">{{include.pub.title}}</h3>

{{ authors }}. {{include.pub.venue}} {{include.pub.date | date: "%Y"}}.<br>
_Project:_ {{ projs | strip }}

{% endunless %}
