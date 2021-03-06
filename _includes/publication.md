{% assign key = include.pub_hash[0] %}
{% assign pub = include.pub_hash[1] %}

{% assign projsize = pub.projects | size %}
{% unless projsize == 0 %}

{% capture authors %}
{% for author in pub.authors %}
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
{% for proj in pub.projects %}
    {% assign matches = site.projects |
        where_exp: "other", "proj == other.tag" %}
    {% for match in matches %}
        [{{match.title}}]({{match.url}})
    {% endfor %}
{% endfor %}
{% endcapture %}

<h3 class="tight-h3">{{pub.title}}
<a href="http://cs.cmu.edu/~beckmann/publications/papers/{{key}}.pdf">[pdf]</a></h3>

{{ authors }}. {{pub.venue}} {{pub.date | date: "%Y"}}. {{pub.note}}<br>
{% unless include.noproject == "true" %}_Project:_ {{ projs | strip }}{% endunless %}

{% endunless %}
