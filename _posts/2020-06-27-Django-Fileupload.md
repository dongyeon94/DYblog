---
layout: post
title:  "Start File upload"
date:   2020-07-03
author: DY
comments: true
categories: Django
---

# Let's Start Django 



---

로컬 디렉토리에 File을 업로드 해보겠습니다. urls.py 파일과 view.py 그리고 file.html 
3개로 만들었습니다.

 


- urls.py

```python

from django.urls import path
from django.conf.urls import url
from . import views

urlpatterns = [
    path('', views.index, name='index'),
    path('t1', views.index2, name='index2'),
    # path('up', views.up , name="up"),
    url(r'^up/$',views.up),
]

```


- view.py

```python

from django.shortcuts import render,redirect
from django.http import HttpResponse , HttpResponseRedirect
import os

from .forms import UploadFileForm



def index(request):
    # return HttpResponse("Hello, world. You're at the polls index.")
    # latest_question_list = Question.objects.order_by('-pub_date')[:5]
    context = {'latest_question_list': "data"}
    cont = {'data': os.system('dir')}
    return render(request, 'polls/index.html',cont)

def index2(request):
    return render(request,"fileupload/index.html",{})

def up(request):
    for count, x in enumerate(request.FILES.getlist("files")):
        def process(f):
            print(count,"  //" ,x)
            with open('D:\programing\pythonprogram\DjangoPage\jango1\mysite\Files\s'+str(x), 'wb+') as destination:
                for chunk in f.chunks():
                    destination.write(chunk)
        process(x)
    return HttpResponse("File(s) uploaded")

```

- index.html

```html

<div>test</div>
<div>



</div>

{% if data %}
    <ul>
    {% for question in latest_question_list %}
        <li><a href="/polls/{{ question.id }}/">{{ question.question_text }}</a></li>
    {% endfor %}
    </ul>
{% else %}
    <p>No polls are available.</p>
{% endif %}

```




---

<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://docs.djangoproject.com/ko/3.0/' ">Django</button> 
</div>
