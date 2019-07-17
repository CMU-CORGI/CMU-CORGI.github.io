# Funding Sources

CORGI is generously funded by

{% for source in site.data.funding %}

  * ![{{ source.name }}]({{ source.image }}){: width="96px"} -- [{{ source.name }}]({{ source.url }})

{% endfor %}

# List of Awards

{% for funds in site.funding %}
{% assign source = site.data.funding[funds.source] %}

## {{ funds.title }}
### ![{{ source.name }}]({{ source.image }}){: width="48px"} -- [{{ source.name }}]({{ source.url }}) 

{{ funds.contents }}

{% endfor %}
