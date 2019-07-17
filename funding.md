# Funding Sources

CORGI is generously funded by

{% for source_hash in site.data.funding %}
{% assign source = source_hash[1] %}

  * ![{{ source.name }}]({{ source.image }}){: width="96px"} -- [{{ source.name }}]({{ source.url }})

{% endfor %}

# List of Awards

{% for funds in site.funding %}
{% assign source = site.data.funding[funds.source] %}

## {{ funds.title }}
### ![{{ source.name }}]({{ source.image }}){: width="48px"} -- [{{ source.name }}]({{ source.url }}) 

{{ funds.contents }}

{% endfor %}
