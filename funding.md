---
title: CORGi Funding
---

# List of Awards

Click on each award to see a list of projects and publications funded.

{% assign funds = site.funding | sort: 'date' | reverse %}
{% for fund in funds %}
{% assign source = site.data.funding[fund.source] %}

<div class="image-and-text">
  <a href="{{ fund.url }}">
     <img src="{{ source.image }}" width="64px" style="margin-right: 10px" />
  </a>
  <h3><a href="{{ fund.url }}">{{fund.title}}</a></h3>
</div>

{% endfor %}
