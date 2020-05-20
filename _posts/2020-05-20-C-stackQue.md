---
layout: post
title:  "C/C++ Stack Que"
date:   2020-05-20
author: DY
comments: true
categories: C
---

scanf(), Array, header <include>과 같은 내용은 제외 하였습니다.

---

## Stack


~~~c++
#include <stdio.h>
#include <stdlib.h>
#include <stdarg.h>
#include <time.h>
#include <stdbool.h>


//stack
int stackMax = 10;
int stack[10];
int top = -1;

int stackisemmty() {
   if (top == -1) {
      return 1;
   }
   else {
      return 0;
   }
}
int stackisfull() {
   if (top == stackMax) {
      return 1;
   }
   else {
      return 0;
   }
}
int stackpeek() {
   return stack[top];
}
int stackpop() {
   int data;
   if (!stackisemmty()) {
      data = stack[top];
      top = top - 1;
      return data;
   }
   else {
      printf("stack is empty\n");
   }
}
int push(int data) {
   if (!stackisfull()) {
      top = top + 1;
      stack[top] = data;
   }
   else {
      printf("stack is full\n");
   }
}


int main(void) {
   // 배열
   printf("hello world\n");


   //stack
   push(3);
   push(4);
   push(5);
   push(6);
   push(7);
   printf("stack peek %d\n", stackpeek());

   stackpop();
   stackpop();
   printf("stack peek %d\n", stackpeek());



   return 0;
}
~~~

Stack 구조는 LIFO로 불립니다. (Last In First Out) 가장 최근에 push 받은 값을 pop했을때 
out 한다는 의미 입니다. 

간단한 예시로는 가장 최근에 했던 명령을 취소 하거나 인터넷 브라우저를 뒤로 돌릴때 활용할 수 있는
자료 구조입니다. 

---




## QUE

~~~ c++

#include <stdio.h>
#include <stdlib.h>
#include <stdarg.h>
#include <time.h>
#include <stdbool.h>



// que
int QueArray[10];
int quemax = 10;
int front = 0;
int rear = -1;
int count = 0;

int peek() {
   return QueArray[front];
}
bool isEmpty() {
   return count == 0;
}

bool isFull() {
   return count == quemax;
}
int size() {
   return count;
}
void insert(int data) {
   if(!isFull() ) {
      if (rear == quemax - 1) {
         rear = -1;
      }

      QueArray[++rear] = data;
      count++;
   }
}
int removeData() {
   int data = QueArray[front++];

   if (front == quemax) {
      front = 0;
   }
   count--;
   return data;
}



int main(void) {
   // 배열
   printf("hello world\n");



   //queue
   insert(3);
   insert(4);
   insert(5);
   insert(6);
   insert(7);
   printf("peek %d \n", peek());

   removeData();
   removeData();
   printf("peek %d \n", peek());

   return 0;
}

~~~

Que 구조는  FIFO로 불립니다. (First In First Out) 처음 입력 받은 값을 Out 한다는 의미입니다.

물류의 선입 선출과 같은 개념입니다.

---


<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://visualstudio.microsoft.com/ko/vs/features/cplusplus/' ">Visual Studio</button> 
</div>
