# Complete List of Publications

See individual [projects](projects.html) for a sorted list of publications.

{% for pub_hash in site.data.publications %}

{% assign pub = pub_hash[1] %}

{% include publication.md pub=pub %}

{% endfor %}
