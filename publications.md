# Complete List of Publications

{% for pub_hash in site.data.publications %}

{% assign pub = pub_hash[1] %}

{% include publication.md pub=pub %}

{% endfor %}
