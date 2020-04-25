---
layout: post
title:  "[키움 open api] 개발 준비"
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

---

## 프로그램 설치

1.Python 설치

먼저 <button onclick="location.href='https://www.python.org/downloads/release/python-377/' ">Python</button> 홈페이지에 가서 python을 다운 받습니다. 
Python3.7버전의 파이썬입니다. 자신의 OS에 맞게 다운 받으시면 됩니다. 버튼을 클릭해서 다운 받으시거나 [https://www.python.org/](https://www.python.org/)  홈페이지에서 Python3를 받으시면 상관 없을것 같습니다.

파이썬의 설치는 설정할것 없이 next만 눌러주시면 됩니다. 


2.Anaconda 설치

사실 아나콘다는 필수로 설치하실 필요는 없습니다. 하지만 Anaconda없이 사용하시려면 Python부터 32bit 파일로 받으셔야 합니다. 

<button onclick="location.href='https://www.anaconda.com/products/individual' "> Anaconda </button> 
홈페이지 UI가 바뀌었네요...?? 일단 제일 아래로 내려서 자신에 OS에 맞게 다운 받으시면 됩니다.(64bit로 받아주세요 굳이 32로 안받아도 됩니다.)


3.IDE 설치

개발하시는 분의 입맛에 따라 설치하셔도 되지만 저는 jetbrain의 <button onclick="location.href='https://www.jetbrains.com/ko-kr/pycharm/' ">Pycharm</button>을 사용했습니다.
추후 개발 환경 설정할때 제가 환경 설정한 대로 포스팅 할거라서 Pycharm설치를 권장드립니다.


4.영웅문 프로그램

<button onclick="location.href='https://www1.kiwoom.com/nkw.templateFrameSet.do?m=m1408000000' ">Kiwoom api</button>
왼쪽 사이드바 하단에 영웅문4 HTS라는 이름이 보입니다. 이 프로그램을 다운받아야 실제로 테스트가 정확한지 확인할 수 있습니다. 

---

## 모듈 설치

1.키움 api 설치 

키움 홈페이지에서 open api를 설치해 주세요 
<button onclick="location.href='https://www1.kiwoom.com/nkw.templateFrameSet.do?m=m1408000000' ">Kiwoom api</button> 
open api + 는 국내 주식  open api w는 해외 주식입니다.
해외 주식은 거래소 거래를 해야 요청을 넣을 수 있으니 open api + 에세 충분히 학습하고 결제를 진행하는걸 추천드립니다.




---

<div style="float: right;">
  <button onclick="location.href='https://www.kiwoom.com/' ">키움증권</button>
  <button onclick="location.href='https://www.jetbrains.com/ko-kr/pycharm/' ">Pycharm</button>
  <button onclick="location.href='https://www.python.org/downloads/release/python-377/' ">Python</button> 
  <button onclick="location.href='https://www.anaconda.com/products/individual' "> Anaconda </button> 
</div>
