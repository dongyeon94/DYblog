---
layout: post
title:  "library에러 해결!"
date:   2020-05-30
author: DY
comments: true
categories: C
---

에러나던  Library 해결했습니다.

## 헤더 파일의 문제

저번에 에러나던 라이브러리 해결했습니다.

* 이전 post
  - [library를 만들어보자](https://dongyeon94.github.io/DYblog/c/2020/05/28/C-libary.html)
  

---

생각보다 간단하게 풀렸습니다. 
해더 파일을 강제로 주입하니 내가 만든 라이브러리가 성공적으로 빌드 됩니다. 
( 윈도우가 보안 차단 한번 먹임)

![image](https://user-images.githubusercontent.com/37605781/83320312-357bad00-a281-11ea-8d78-115185cae497.png)

.h 파일 즉 헤더파일이 위치한 절대경로를 강제로 주입했더니

![image](https://user-images.githubusercontent.com/37605781/83320378-d8342b80-a281-11ea-8157-7ab8e4751472.png)

원했던 결과였던 200을 리턴하게 됩니다 ( 헤더 파일에 200을 리턴하는 int 메소드 만들어놨음)

 

---


<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://visualstudio.microsoft.com/ko/vs/features/cplusplus/' ">Visual Studio</button> 
</div>
