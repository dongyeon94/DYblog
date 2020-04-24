---
layout: page
title: "cate"
permalink: /cate/
main_nav: true
---


<div>
<h2>cate gory test</h2>
</div>
{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h2 id="{{cat}}">{{ cat | capitalize }}</h2>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  

  
{% endfor %}
<br>
