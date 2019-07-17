{% for funds in site.funding %}
{% assign source = site.data.funding[funds.source] %}

## ![{{ source.name }}]({{ source.image }}){: width="48px"} {{ funds.title }}
### [{{ source.name }}]({{ source.url }}) 

{{ funds.contents }}

{% endfor %}
