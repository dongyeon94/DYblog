---
layout: post
title:  "Spring Boot validation"
date:   2020-07-14
author: DY
comments: true
categories: Daily
---


## Spring boot Validation

Spring boot를 공부하면서 doc에서 신기한 부분을 찾아서 업로드 합니다. 


docs 내용은 아래 링크에서 확인할 수 있습니다.
* [https://spring.io/guides/gs/validating-form-input/](https://spring.io/guides/gs/validating-form-input/)

코드를 따라서 코딩하고 테스트를 하는 과정에서 한가지 해프닝이 생겼습니다.
결과에서 아래 사진처럼 에러가 나타나야 하는데

![image](https://user-images.githubusercontent.com/37605781/87441469-161cc180-c62e-11ea-8df6-a74dca9b6c4a.png)


제가 작성을하니 코드가.. 통과 되었습니다.  

![image](https://user-images.githubusercontent.com/37605781/87441606-3d738e80-c62e-11ea-8239-163620bf76dc.png)


여기저기 찾아보고 프로젝트를 다시 만들어보고 수없이 구글링을 했지만 생각보다 답은 가까운곳에.. 있었습니다.

![image](https://user-images.githubusercontent.com/37605781/87441754-727fe100-c62e-11ea-9cfb-46008a3630d5.png)

Release version이 제 프로젝트가 더 높아서 괜찮을줄 알았는데 버전에 따라 지원하는 방식이 달랐던 것 같습니다.
버전에 대한 에러인것을 확인했으니 이제 남은 일은 다른 라이브러리 버전을 맞추거나 혹은 높은 버전에서 
validation을 어떻게 작성하는지 찾아 봐야 할 것 같습니다.



---
<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/' ">Spring Boot Reference</button> 
</div>
