---
order: 1
display-title: "Organism"
tooltip: "List of organisms represented by pathways in the database" 
btn-class: "btn-organism btn-pill"
---

<h1>Pathway Figures by Organism</h1>
<p>Browse species below to identify pathway figures.</p>
{% assign type-group = site.organisms | group_by: "group" | sort: "name"  %}
{% for type in type-group %}
<section class="facet">
  <div class="facet-header"> 
    <h2 class="facet-title">{{ type.name }}</h2>
  </div>
  <div class="facet-body" id="{{ type.name }}">
  {% assign sorted_items = type.items | sort: "common" %}
  {% for x in sorted_items %} 
    <a class="btn btn-sm btn-pill btn-organism" href="{{ x.url }}" title="{{x.latin}}">{{ x.common }}</a>
  {% endfor %} 
  </div>
</section>
{% endfor %}
