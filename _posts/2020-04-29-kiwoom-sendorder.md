---
layout: post
title:  "[키움 open api] 주문 기능 구현"
date:   2020-05-11
author: DY
comments: true
categories: Outsourcing
---


## Day3

키움 Open API로 매수/매도 주문을 시행해 보겠습니다.


```python

kiwoom.SendOrder("");

```


---



## 코드 리뷰

sendOrder주문을 통해 계좌번호, 비밀번호, 종목 코드 등을 입력해서 키움에 주문을 보냅니다.
주문에 성공하면 0 을 리턴하게 됩니다.

자세한 정보는, 개인정보가 많이 포함되어있어 작성하지 못합니다.ㅜㅜ

개발자 가이드를 보면 sendOrder 주문에는 매수/매도 주문과 oco / if done 주문을 할 수 있습니다. 
영웅문에서 가능한 모든 기능을 api로 주문할 수 있습니다. 추가로 주문에 실패하면 0을 리턴하지 않습니다.

* 추가사항

1. 추가로 커넥터에 비밀번호를 입력해야 주문이 진행됩니다. 

2. Open-w API 사용하는 분들은 본인들이 사용하는 거래소에 결제를 해야 진행가능합니다. (거래소 마다 $170 정도 합니다.)

3. api는 초당 주문 제한이 있어 1초에 3회 정도만 주문 하시는걸 권장합니다.


---
<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://www.kiwoom.com/' ">키움증권</button>
  <button onclick="location.href='https://www.jetbrains.com/ko-kr/pycharm/' ">Pycharm</button>
  <button onclick="location.href='https://www.python.org/downloads/release/python-377/' ">Python</button> 
  <button onclick="location.href='https://www.anaconda.com/products/individual' "> Anaconda </button> 
</div>
