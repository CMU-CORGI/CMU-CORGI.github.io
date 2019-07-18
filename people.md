---
title: CORGi People
---

# Faculty

{% assign faculty = site.people |
  where_exp:"person","person.title contains 'Professor'" %}
{% for person in faculty %}

### {{ person.name }} --- [web]({{ person.webpage }})

![{{person.name}}]({{person.image}}){: height="250px"}

{{ person.title }} in {{ person.dept }}.

{% endfor %}

# PhD Students

{% assign students = site.people |
  where:"title","PhD student" |
  where_exp:"person","person.end == ''" |
  sort: 'name' | reverse |
  sort: 'start' | reverse %}
{% for person in students %}

### {{ person.name }} {%
  if person.webpage %}--- [web]({{ person.webpage }}){% endif %} --- since {{ person.start | date: "%Y" }}

![{{person.name}}]({{person.image}}){: height="200px"}

{{ person.output }}

{% endfor %}

# Masters and Undergrad Students

{% assign bsstudents = site.people |
   where_exp:"person","person.title == 'BS'" %}
{% assign msstudents = site.people |
   where_exp:"person","person.title == 'MS'" %}
{% assign students = bsstudents | concat: msstudents |
   where_exp:"person","person.end == ''" |
   sort: 'name' | reverse |
   sort: 'start' | reverse %}
{% for person in students %}

### {{ person.name }} {%
  if person.webpage %}--- [web]({{ person.webpage }}){% endif %} --- since {{ person.start | date: "%Y" }}

{% if person.image %}![{{person.name}}]({{person.image}}){: height="200px"}{% endif %}

{{ person.title }} in {{ person.dept }}

{{ person.output }}

{% endfor %}

# Alumni

{% assign students = site.people |
  where_exp:"person","person.end != ''" |
  sort: 'name' | reverse |
  sort: 'end' | reverse %}
{% for person in students %}

### {{ person.name }} {%
  if person.webpage %}--- [web]({{ person.webpage }}){% endif %} --- {{
  person.start | date: "%Y" }} to {{ person.end | date: "%Y" }}

{% if person.image %}![{{person.name}}]({{person.image}}){: height="200px"}{% endif %}

{{ person.title }} in {{ person.dept }}.
{{ person.content }}

{% endfor %}
