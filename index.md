---
layout: tab
---
<h2> <u> Card Blog Posts </u> </h2>
<br>
{% for post in site.posts) %}
  {% assign remainder = forloop.index | modulo: 3 | minus: 1%}
  {% if remainder == 0 and forloop.index != 1 %}
  </div>
  {% endif %}
  {% if remainder == 0 %}
  <div class="row"> 
  {% endif %}
  <div class="card bg-dark shadow-lg p-3 mb-5 col-md-3">
    <div class="card-title">
      Blog Post No. {{ post.number }}
      <br>
      {{ post.title }}
      <br>
      Date: {{ post.date | date_to_string }}
    </div>
    <div class="card-body">
      {{post.content}}
    </div>
  </div>
{% endfor %}
<br>
