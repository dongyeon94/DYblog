---
layout: post
title:  "[키움 open api] 개발 준비"
date:   2020-04-25
author: DY
comments: true
categories: Outsourcing
---


## Day2

키움 Open API로 로그인 화면을 구현해 보겠습니다. 

일단 코드부터,,

```python

import sys
from PyQt5.QtWidgets import *
from PyQt5.QAxContainer import *

class MyWindow(QMainWindow):
    def __init__(self):
        # 초기 setup 모듈 로딩 등
        super().__init__()

        self.setWindowTitle("PyStock")
        self.setGeometry(300, 150, 400, 800)
        self.kiwoom = QAxWidget("KFOpenAPI.KFOpenAPICtrl.1")

        # 로그인
        login_btn = QPushButton("로그인", self)
        login_btn.move(20, 20)
        login_btn.clicked.connect(self.login_clicked)

        info_btn = QPushButton('로그인 확인', self)
        info_btn.move(20, 70)
        info_btn.clicked.connect(self.login_info)
        
    def login_clicked(self):
        ret = self.kiwoom.dynamicCall("CommConnect(0)")
        print(ret)

    def staate_clicked(self):
        if self.kiwoom.dynamicCall("GetConnectState()") == 0:
            self.statusBar().showMessage("Not connected")
            print('---------------------------------')
            print('로그인 실패')
            print('---------------------------------')
        else:
            self.statusBar().showMessage("Connected")
            print('---------------------------------')
            print('로그인 성공')
            print('---------------------------------')

    def login_info(self):
        info_user_id = self.kiwoom.dynamicCall('GetLoginInfo("USER_ID")')
        info_user_name = self.kiwoom.dynamicCall('GetLoginInfo("USER_NAME")')
        info_account_cnt = self.kiwoom.dynamicCall('GetLoginInfo("ACCOUNT_CNT")')
        info_accno = self.kiwoom.dynamicCall('GetLoginInfo("ACCNO")')
        info_key_bsecgb = self.kiwoom.dynamicCall('GetLoginInfo("KEY_BSECGB")')
        info_firew_secgb = self.kiwoom.dynamicCall('GetLoginInfo("FIREW_SECGB")')
        self.account.setText(info_accno.split(';')[0])        
        
if __name__ == "__main__":
    app = QApplication(sys.argv)
    myWindow = MyWindow()
    myWindow.show()
    app.exec_()


```


---

## 개발에 앞서

개발을 하기전에 제일 먼저 해야하는게 있습니다. 
1. 프로그램을 켠다?
2. 예제 샘플을 검색한다?
3. 뭐 다른 방법이 있을것이다.??

3가지 예시 전부 틀렸습니다. 가장 먼저해야 하는 행동은 개발자 가이드를 읽어야 합니다. 개발자 가이드에
개발에 필요한게 상당히 많습니다. 심지어 예제 코드가 함께?? 아니! 검색을 안해도 되잖아?!!

저는 철저히.. 가이드 보고 개발했습니다.

---

## 코드 리뷰

일단 라이브러리 부터 선언하고 시작합니다. 그다음에 QMainWindow라는 PyQt5안에 있는 모듈을 
불러오게 됩니다. 여기서 init 함수를 통해 GUI의 기초틀을 만듭니다. QpushButton으로 버튼을 만들고
버튼 위치를 정해주고 클릭되었을때 발생하는 이벤트를 주었습니다. 
이벤트는 따로 class 안에 함수로 정의 했습니다. 

가장 중요한 것은 아래 모듈을 불러와야 한다는 것입니다. (이거 없으면 api접근이 안됩니다.) 
```Python

QAxWidget("KFOpenAPI.KFOpenAPICtrl.1")

```

나머지 dynamicCall안에 String으로 요청한 기능들은 개발자 가이드에 보면 설명이 있습니다. 
CommConnect(0) = 로그인 모듈을 실행합니다.
GetConnectState() = 로그인 상태를 출력합니다. (0 출력시 로그인 성공)

프로그램을 실행하고 로그인 버튼을 눌렀을때 아래와 같은 화면이 뜨면 성공입니다.

![키움](https://user-images.githubusercontent.com/37605781/80595302-781e4f80-8a5f-11ea-8ae0-0493eb6efa9e.jpg)
(키움 증권은 따로 나옵니다. GUI안에 생긴거 아님!!)
---
<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://www.kiwoom.com/' ">키움증권</button>
  <button onclick="location.href='https://www.jetbrains.com/ko-kr/pycharm/' ">Pycharm</button>
  <button onclick="location.href='https://www.python.org/downloads/release/python-377/' ">Python</button> 
  <button onclick="location.href='https://www.anaconda.com/products/individual' "> Anaconda </button> 
</div>
