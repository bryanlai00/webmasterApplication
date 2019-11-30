---
layout: tab
---
<center>
<div class="card shadow p-3 mb-5 black col-md-6">
<h4> Card Blog Posts </h4>
</div>
</center>
<br>
{% for post in site.posts) %}
  {% assign remainder = forloop.index | modulo: 3 | minus: 1%}
  {% if remainder == 0 and forloop.index != 1 %}
  </div>
  {% endif %}
  {% if remainder == 0 %}
  <div class="row"> 
  {% endif %}
  <div class="card black shadow-lg p-3 mb-5 col-md-3">
    <div class="card-title">
      {{ post.title }}
    <div class="nd">
      Blog Post No. {{ post.number }}
      <br>
      Date: {{ post.date | date_to_string }}
    </div>
    </div>
    <div class="card-body">
      {{post.content}}
    </div>
  </div>
{% endfor %}
<br>
