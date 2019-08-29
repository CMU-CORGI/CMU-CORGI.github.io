# Projects

Click on a project to learn more about its people, publications, and funding.

{% assign projects = site.projects |
  sort: 'title' | reverse |
  sort: 'start' | reverse %}

<div class="project-grid">

{% for project in projects %}

<div markdown="1">

### [{{ project.title }}]({{project.url}})

<a href="{{project.url}}">
<img src="{{project.image}}" alt="{{project.title}}" class="project" />
</a>

{{project.content}}

</div>

{% endfor %}

</div>

