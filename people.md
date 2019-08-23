---
title: CORGi People
---

# Faculty

{% assign faculty = site.people |
  where_exp:"person","person.title contains 'Professor'" %}
{% for person in faculty %}

### {{ person.name }}

{% if person.webpage %}<a href="{{person.webpage}}">{% endif %}
<img src="{{person.image}}" alt="{{person.name}}" class="person" />
{% if person.webpage %}</a>{% endif %}

{{ person.title }} in {{ person.dept }}.

{% endfor %}

# PhD Students

{% assign students = site.people |
  where:"title","PhD student" |
  where_exp:"person","person.end == ''" |
  sort: 'name' | reverse |
  sort: 'start' | reverse %}

<div class="people-grid">

{% for person in students %}

<div markdown="1">

### {{ person.name }} ({{ person.start | date: "%Y" }} -- )

{% if person.webpage %}<a href="{{person.webpage}}">{% endif %}
<img src="{{person.image}}" alt="{{person.name}}" class="person" />
{% if person.webpage %}</a>{% endif %}

{{ person.output | remove: '<p>' | remove: '</p>' }}

</div>

{% endfor %}

</div>

# Masters and Undergrad Students

{% assign bsstudents = site.people |
   where_exp:"person","person.title == 'BS'" %}
{% assign msstudents = site.people |
   where_exp:"person","person.title == 'MS'" %}
{% assign students = bsstudents | concat: msstudents |
   where_exp:"person","person.end == ''" |
   sort: 'name' | reverse |
   sort: 'start' | reverse %}

<div class="people-grid">

{% for person in students %}

<div markdown="1">

### {{ person.name }} ({{ person.start | date: "%Y" }} -- )

{% if person.webpage %}<a href="{{person.webpage}}">{% endif %}
{% if person.image %}<img src="{{person.image}}" alt="{{person.name}}" class="person" />{% endif %}
{% if person.webpage %}</a>{% endif %}

{{ person.title }} in {{ person.dept }}. {{ person.output | remove: '<p>' | remove: '</p>' }}

</div>

{% endfor %}

</div>

# Alumni

{% assign students = site.people |
  where_exp:"person","person.end != ''" |
  sort: 'name' | reverse |
  sort: 'end' | reverse %}

<div class="people-grid">

{% for person in students %}

<div markdown="1">

### {{ person.name }} ({{ person.start | date: "%Y" }} -- {{ person.end | date: "%Y" }})

{% if person.webpage %}<a href="{{person.webpage}}">{% endif %}
{% if person.image %}<img src="{{person.image}}" alt="{{person.name}}" class="person" />{% endif %}
{% if person.webpage %}</a>{% endif %}

{{ person.title }} in {{ person.dept }}. {{ person.output | remove: '<p>' | remove: '</p>' }}

</div>

{% endfor %}

</div>
