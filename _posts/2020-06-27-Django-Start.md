---
layout: post
title:  "Django도 해보자"
date:   2020-06-27
author: DY
comments: true
categories: Django
---

# Let's Start Django 

* [My First Django Web](https://programmers.co.kr/learn/courses/30/lessons/42888)

---

Django web page를 만들어 보겠습니다.
 - 파이썬과 라이브러리가 설치되어있다는 가정으로 진행됩니다.

먼저 CMD화면 혹은 Terminal에서 Django project를 만들 디렉토리로 이동합니다. 해당 화면에서 
~~~
django-admin startproject mysite  (window)
django-admin startproject mysite  (Linux/Mac)
~~~
을 입력해줍니다.


에러가 없다면 자동으로 폴더와  python파일들이 생성됩니다. 
 
---

이제 콘솔창의 디렉토리를 새로 설치된 mysite로 이동합니다. 
이동한 mysite 위치에서 

~~~
py manage.py startapp polls     ( window)
python manage.py startapp polls (Linux / Mac)
~~~

를 입력하면 이제 뷰를만들 polls 디렉토리가 만들어 지게 됩니다. 이제 다 왔습니다.
실제로 뷰를 만들거나 기능을 만드는 것은 polls디렉토리에서
 진행하 지만 만드는 것은 다음에 하고 main page만 띄워보겠습니다.



---

아까 콘솔창을 끄지 않았다면 mysite에 위치에 있는 상태입니다. 해당 위치에서

~~~
py manage.py runserver 
python manage.py runserver 
~~~

명령어를 실행하면 쥬르르륵 메시지가 뜨면서 로컬 서버가 돌아갑니다. 
이제 [http://127.0.0.1:8000](http://127.0.0.1:8000/polls/up/)주소로 들어가 보겠습니다. 

![image](https://user-images.githubusercontent.com/37605781/85914567-0e150180-b87a-11ea-873d-26fde8e1708d.png)

위와 같은 사진이 뜨면 성공입니다. 


---

<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://docs.djangoproject.com/ko/3.0/' ">Django</button> 
</div>
