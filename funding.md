# Funding Sources

{% for source_hash in site.data.funding %}{% assign source = source_hash[1] %}[ ![{{ source.name }}]({{ source.image }}){: width="96px"} ]({{source.url}}){% endfor %}

# List of Awards

{% for funds in site.funding %}
{% assign source = site.data.funding[funds.source] %}

## ![{{ source.name }}]({{ source.image }}){: width="32px"} {{ funds.title }}

{{ funds.contents }}

{% endfor %}
