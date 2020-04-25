---
layout: post
title:  "<키움 open api> 개발 준비"
date:   2020-04-25
author: DY
comments: true
categories: Outsourcing
---

---

## Day1

키움 open api를 개발할수 있는 언어의 종류는 정해져있지 않습니다.
  - 언어 예시
    - C#
    - C++
    - java
    - Python

저는 여기서 Python을 선택해서 개발을 진행했습니다. 개발에 앞서 먼저 필수적으로 설치해야 하는 프로그램과 모듈이 있습니다.

  - 프로그램
    1. Python
    2. Anaconda

  - 모듈
    1. 키움 open api +
    2. 키움 open api W 

** 모든 프로그램 및 모듈의 다운로드 링크는 제일 아래 버튼을 클릭하면 이동할 수 있습니다. 

---

## 프로그램 설치

1.Python 설치

먼저Python 홈페이지에 가서 python을 다운 받습니다. 
Python3.7버전의 파이썬입니다. 자신의 OS에 맞게 다운 받으시면 됩니다. 버튼을 클릭해서 다운 받으시거나 [https://www.python.org/](https://www.python.org/)  홈페이지에서 Python3를 받으시면 상관 없을것 같습니다.

C:\Program Files 안에 Python이라는 새로운 폴더를 만들어  해당 경로로 Python파일을 설치해주세요 추후 환경 설정에 굉장한 도움을 줍니다.  


2.Anaconda 설치

사실 아나콘다는 필수로 설치하실 필요는 없습니다. 하지만 Anaconda없이 사용하시려면 Python부터 32bit 파일로 받으셔야 합니다. 

홈페이지 UI가 바뀌었네요...?? 일단 제일 아래로 내려서 자신에 OS에 맞게 다운 받으시면 됩니다.(64bit로 받아주세요 굳이 32로 안받아도 됩니다.)

C:\Program Files 안에 Anaconda라는 새로운 폴더를 만들어  해당 경로로 Anaconda프로그램을 설치해주세요 추후 환경 설정에 굉장한 도움을 줍니다.


3.IDE 설치

개발하시는 분의 입맛에 따라 설치하셔도 되지만 저는 jetbrain의 Pycharm을 사용했습니다.
추후 개발 환경 설정할때 제가 환경 설정한 대로 포스팅 할거라서 Pycharm설치를 권장드립니다.


4.영웅문 프로그램

키움 홈페이지에 가보면 왼쪽 사이드바 하단에 영웅문4 HTS라는 이름이 보입니다. 이 프로그램을 다운받아야 실제로 테스트가 정확한지 확인할 수 있습니다. 

---

## 모듈 설치

1.키움 api 설치 

키움 홈페이지에서 open api를 설치해 주세요 open api + 는 국내 주식  open api w는 해외 주식입니다.
해외 주식은 거래소 거래를 해야 요청을 넣을 수 있으니 open api + 에세 충분히 학습하고 결제를 진행하는걸 추천드립니다.

---

## 환경 설정

1.Anaconda 설정

다른 언어는 모르겠는데 Python으로 키움 API르 사용하기 위해선 32bit Python이 필요합니다. 때문에 64bit로 받은 Python을 32bit으로 설정해줘야합니다.
Anaconda를 정상적으로 설치하셨으면 

![anaconda](https://user-images.githubusercontent.com/37605781/80280115-0a131900-873d-11ea-99cf-6aa36202c581.PNG)

가 설치되어 있습니다. 해당 프로그램을 실행하면 아래와 같은 화면이 나타나게 됩니다.
![navi](https://user-images.githubusercontent.com/37605781/80280216-b94ff000-873d-11ea-89b6-f01d247b4d74.jpg)

제 화면에는 base(root), py37_32, python32 3개가 있는데 처음 설치하면 base(root) 한개만 있는게 맞습니다. 이제 py37_32 환경을 추가 해야합니다.
base(root) 옆에 작은 삼각형을 누르면 open Terminal버튼이 있습니다.  
버튼을 누르면 검은 CMD창이 하나 뜨게 되는데 그 안에 
~~~
set CONDA_FORCE_32BIT=1
conda create -n py37_32 python=3.7 anaconda
~~~
를 입력하시면 중간에 (y/n)를 선택하는 부분이 1개인가 2개인가 나옵니다. 모두 y를 선택하고 진행해주세요

마지막으로
~~~
activate py37_32
~~~

를 입력하시면 환경에 py37_32가 생성되게 됩니다.



2.라이브러리 다운

이제 설정이 거의다 끝났습니다. 필요한 라이브러리만 다운받으면 됩니다.
새로 만든 py37_32환경에 Terminal을 켜봅시다. (오른쪽 작은 삼각형을 누르면 켜집니다.)
그 안에 

~~~
pip install PyQt5
~~~
이것만 입력해 주시면 환경 설정은 끝입니다. 

---

## IDE 개발 환경 설정

** Pycharm 을 설치하신 분에 한에서 적용됩니다.

Pycharm을 켜면 file -> setting에 interpreter를 설정할수 있는 부분이 있습니다. 아래 사진 처럼 add를 눌러주세요
![pycahrm](https://user-images.githubusercontent.com/37605781/80280535-9a525d80-873f-11ea-86ff-e38197f23098.jpg)

버튼을 누르면 아래 사진 처럼 왼쪽에 탭에서 conda -> Exisiting enviroment를 선택하면 됩니다.
이제 py37_32안에 Python.exe를 설정해야 합니다. 
그런데 방금전 Anaconda를 설치한 위치가 어디인지 기억하시나요? 처음부터 잘 따라오셨다면 C:\Program Files 안에 Anaconda라는 폴더가 있을겁니다.
여기 안에 env라는 폴더가 있는데 폴더를 열어보면 이전에 없었던 py37_32폴더가 생깁니다.
이제 폴더안에 있는 python.exe파일을 클릭하고 ok를 누르면 환경설정이 완료됩니다. 이제 우리는 py37_32환경에서 프로그래밍을 진행할 수 있습니다.
![envir](https://user-images.githubusercontent.com/37605781/80280595-f917d700-873f-11ea-8717-b8c8efc2e1f6.JPG)


---

<div style="float: right;">
  <button onclick="location.href='https://www.kiwoom.com/' ">키움증권</button>
  <button onclick="location.href='https://www.jetbrains.com/ko-kr/pycharm/' ">Pycharm</button>
  <button onclick="location.href='https://www.python.org/downloads/release/python-377/' ">Python</button> 
  <button onclick="location.href='https://www.anaconda.com/products/individual' "> Anaconda </button> 
</div>
