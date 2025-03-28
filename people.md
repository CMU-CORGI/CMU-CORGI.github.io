---
title: CORGi People
---

# Faculty

{% assign faculty = site.people |
  where_exp:"person","person.title contains 'Professor'" %}
{% for person in faculty %}

### [{{ person.name }}]({{person.url}})

<a href="{{person.url}}">
<img src="{{person.image}}" alt="{{person.name}}" class="person" />
</a>

<!-- {{ person.title }} in {{ person.dept }}. -->

{% endfor %}

# Current PhD Students

{% assign students = site.people |
  where:"title","PhD student" |
  where_exp:"person","person.end == ''" |
  sort: 'name' | reverse |
  sort: 'start' %}

<div class="people-grid">

{% for person in students %}

<div markdown="1">

### [{{ person.name }}]({{person.url}}) ({{ person.start | date: "%Y" }} -- )

<a href="{{person.url}}">
<img src="{{person.image}}" alt="{{person.name}}" class="person" />
</a>

</div>

{% endfor %}

</div>

# Current Masters and Undergrad Students

{% assign bsstudents = site.people |
   where_exp:"person","person.title == 'BS'" %}
{% assign msstudents = site.people |
   where_exp:"person","person.title == 'MS'" %}
{% assign students = bsstudents | concat: msstudents |
   where_exp:"person","person.end == ''" |
   sort: 'name' | reverse |
   sort: 'start' %}

<div class="people-grid">

{% for person in students %}

<div markdown="1">

### [{{ person.name }}]({{person.url}}) ({{ person.start | date: "%Y" }} -- )

{% if person.image %}
<a href="{{ person.url }}">
<img src="{{person.image}}" alt="{{person.name}}" class="person" />
</a>
{% endif %}

</div>

{% endfor %}

</div>

# Corgis

{% assign corgis = site.people |
  where_exp: "corgum", "corgum.title contains 'Corgi'" |
  sort: 'name' | reverse |
  sort: 'start' %}

<div class="people-grid">

{% for corgum in corgis %}

<div markdown="1">

### [{{ corgum.name }}]({{corgum.url}}) ({{ corgum.start | date: "%Y" }} -- {{ corgum.end | date: "%Y" }})

<a href="{{corgum.url}}">
<img src="{{corgum.image}}" alt="{{corgum.name}}" class="person" style="height: 150px !important; width: auto !important; margin-right: 10px" />
</a>

</div>

{% endfor %}

</div>

<br>

# Graduated PhDs

{% assign students = site.people |
  where_exp:"person","person.end != ''" |
  sort: 'name' | reverse |
  sort: 'end' | reverse %}

<div class="people-grid">

{% for person in students %}

{% if person.dissertation %}
{% unless person.title contains 'Corgi' %}

<div markdown="1">

### [{{ person.name }}]({{person.url}}) ({{ person.start | date: "%Y" }} -- {{ person.end | date: "%Y" }})

<a href="{{person.url}}">
<img src="{{person.image}}" alt="{{person.name}}" class="person" />
</a>

{{ person.title }} in {{ person.dept }}. Dissertation: <i>{{ person.dissertation }}</i>.{% if person.after %} After CORGi: {{person.after}}.{% endif %}

</div>

{% endunless %}
{% endif %}

{% endfor %}

</div>

# Former Members

{% assign students = site.people |
  where_exp:"person","person.end != ''" |
  sort: 'name' | reverse |
  sort: 'end' | reverse %}

<div class="people-grid">

{% for person in students %}

{% unless person.dissertation %}
{% unless person.title contains 'Corgi' %}

<div markdown="1">

### [{{ person.name }}]({{person.url}}) ({{ person.start | date: "%Y" }} -- {{ person.end | date: "%Y" }})

{{ person.title }} in {{ person.dept }}. {{person.content | remove: "<p>" | remove: "</p>" }}{% if person.after %} After CORGi: {{person.after}}.{% endif %}

</div>

{% endunless %}
{% endunless %}

{% endfor %}

</div>

