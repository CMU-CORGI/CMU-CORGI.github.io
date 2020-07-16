# Projects

Click on a project to learn more about its people, publications, and funding.

{% assign projects = site.projects |
  sort: 'title' | reverse |
  sort: 'start' | reverse %}

<div class="project-grid">

{% for project in projects %}

<div markdown="1">

### [{{ project.title }}]({{project.url}})

{{project.summary}}

<center>
<a href="{{project.url}}">
<img src="{{project.image}}" alt="{{project.title}}" class="project" />
</a>
</center>

</div>

{% endfor %}

</div>

