# Complete List of Publications

See individual [projects](projects.html) for a sorted list of publications.

{% for pub_hash in site.data.publications %}

{% include publication.md pub_hash=pub_hash %}

{% endfor %}
