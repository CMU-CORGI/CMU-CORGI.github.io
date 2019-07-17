{% for funds in site.funding %}
{% assign source = site.data.funding[funds.source] %}

# {{ funds.title }}
## [{{ source.name }}]({{ source.url }}) ![{{ source.name }}]({{ source.image }}){: width="36px}

{{ funds.contents }}

{% endfor %}
