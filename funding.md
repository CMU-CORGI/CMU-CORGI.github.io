---
title: CORGi Funding
---

# List of Awards

Click on each award to see a list of projects and publications funded.

{% assign funds = site.funding | sort: 'date' | reverse %}
{% for fund in funds %}
{% assign source = site.data.funding[fund.source] %}

### ![{{ source.name }}]({{ source.image }}){: width="32px"} {{ fund.title }}

{{ fund.contents }}

{% endfor %}
