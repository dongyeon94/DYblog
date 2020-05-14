---
layout: page
title: "Posts"
permalink: /posts/
main_nav: true
---

<h2>Tags</h2>
<div class="category" style=" height: 200px;">
        
    <div class="category-nav" style="font-size: 30px;border-bottom: 1px solid #dddddd; border-top: 1px solid #dddddd;">
        <div style="height: 10px;"></div>
        
        <button class="back-joon" onclick="indexMove('backjoon')"> Backjoon</button>
        <button class="programmers" onclick="indexMove('programmers')"> Programmers</button>
        <button class="Outsourcing" onclick="indexMove('Outsourcing')"> Outsourcing</button>
        <button class="Daily" onclick="indexMove('Daily')"> Daily</button>
        <button class="Daily" onclick="indexMove('C')"> C</button>
        <button class="Daily" onclick="indexMove('FG')"> FG</button>
        <div style="height: 10px;"></div>
    </div>
    
</div >


{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h2 id="{{cat}}">{{ cat | capitalize }}</h2>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
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



<script src="//code.jquery.com/jquery-3.3.1.min.js"></script>
<script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
<script type="text/javascript">
function indexMove(variable) {
    var id =  variable;
    console.log('test good');
    console.log('variable : '+variable);
    var offset = $('#'+variable).offset();
    $('html,body').animate({scrollTop : offset.top-200},400);
    
    console.log(offset.top);
}
</script>
