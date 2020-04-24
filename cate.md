---
layout: page
title: "cate"
permalink: /cate/
main_nav: true
---
<div>
{% site %}
</div>
<br><br><br><br>
{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h2 id="{{cat}}">{{ cat | capitalize }}</h2>
  <h2> test</h2>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  
  
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>
