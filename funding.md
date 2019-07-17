{% for funds in site.funding %}

  * {{ funds.title }} - {{ funds.source }} : {{ funds.contents }}

{% endfor %}
