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

   <div>{%  site  %}</div>
   
   <ul>
   {% for post2 in site %}
      <li>
        <div>{% post2 %}</div>
      </li>
   </ul>
   
  <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
    </li>
  {% endfor %}
  </ul>
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>
