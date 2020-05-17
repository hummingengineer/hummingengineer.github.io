---
title: "[C] 5. 조건문"
excerpt: "(if, switch) Select statement"
categories:
  - C
tags:
  - c
  - if
  - switch
  - ternary-operator
---
{{ page.excerpt }}
* * *

## 조건문(Selection statement)
- 조건에 따라서 실행하는 구문(statement)이 달라지는 것
- if / switch / 삼항연산자

## if 조건문
```c
if (조건식1) {
  실행구문1
} else if (조건식2) {
  실행구문2
} else {
  실행구문3
}
```
- 조건식이 True/False에 따라서 구문의 실행 여부를 판단
- 3가지 형태가 있음
  - if
  - if - else
  - if - else if - else
- 조건식의 결과는 항상 True(0이외의 다른 값) or False(0)

## 삼항연산자(ternary operator)
```
  조건식 ? 실행구문1 : 실행구문2
```
- ?(물음표)와 :(콜론)을 구성
- 조건식이 true일 경우 실행구문1 수행, 그렇지 않고,
- 조건식이 false인 경우 실행구문2 수행
- Return문과 함께 사용되는 경우도 있음
```c
return i > j ? i : j;
```

## switch문
```c
switch (조건식) {
  case label1: 실행구문1; break;
  case label2: 실행구문2; break;
  default: 실행구문3;
```
- 여러 조건에서 해당하는 조건의 문장을 실행
- If-else if-else 문과 유사한 기능 그렇지만 실행이 빠르고 가독성이 좋음
- switch – case 로 구성
  - 조건식
    - 반드시 괄호로 묶어야 함
    - 결과는 정수와 문자로 한정(실수형은 오류)
  - switch문 조건식에 정수와 문자만 사용할 수 있는 이유
    - switch문 조건식에는 원칙으로는 정수형식만 사용할 수 있기 때문
    - C에서 문자는 정수(ASCII코드)로 다루어지기 때문
  - Label
    - 정수 또는 문자의 상수만 사용할 수 있음
  - Break
    - switch 문을 종료하고 다음 코드를 실행하는 역할
  - Default
    - If문에서 else와 같은 역할, 모든 case가 아닌 경우 실행, 생략가능
- switch와 break문의 관계
  - Break문이 있는 경우 break문을 실행하여 switch문을 종료
  - Break문이 없는 경우 해당조건 이후의 모든 case의 실행구문을 동작
