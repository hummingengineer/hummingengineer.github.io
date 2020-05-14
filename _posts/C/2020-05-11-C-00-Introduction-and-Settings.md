---
title: "[C] 0. 시작하기, 세팅"
excerpt: "C언어의 개요와 개발 환경 설정"
categories:
  - C
tags:
  - c
  - introduction
  - setting
---
{{ page.excerpt }}
* * *

## C언어
- 프로그래밍 언어
  - 컴퓨터와 사람과의 사이에서 대화를 위한 공통의 대화 수단
  - C언어, C++, Java, Python, …
- C언어
  - 작고 빠른 프로그램을 개발하기 위해 설계
  - 대분분의 다른 프로그래밍 언어 보다 더 낮은 수준
  - Embedded 환경에 적합

## C언어 - 작동 방식
- 사람의 언어 != 기계어
  - 기계어를 직접 학습하기에는 어려움이 있음
  - 번역(통역) 하는 프로그램(컴파일러, complier)을 통해 의사 소통
  - 컴파일(compile)이라는 과정을 통해 기계어로 번역

## 컴파일러(Compiler)
- 컴파일러
  - 사람의 언어를 기계어로 번역 하는 역할
  - 대표적인 예) GCC, Clang
- 컴파일
  - 고급언어(C언어)로 작성된 컴퓨터 프로그램을 기계어로 번역하는 과정

## C언어의 특징
- 1971년 UNIX 개발을 위해 Dennis Ritchie와 Ken Thompson이 개발
- 절차지향적 특성을 가짐
  - 정해진 순서의 실행흐름을 중시
- C언어로 작성된 프로그램은 이식성이 좋음
  - CPU의 종류에 상관없이 실행이 가능
- C언어로 구현된 프로그램은 좋은 성능을 보임
  - 상대적으로 요구하는 메모리의 양이 적고, 속도를 저하시키는 요소를 최소화함

## C언어 개발 환경
- Editor: Visual Studio Code(VS Code)
  - <https://code.visualstudio.com/>
- OS: windows 10
- Compiler: mingw-w64 GCC
  - <https://sourceforge.net/projects/mingw-w64/>

## GCC(ming64) install
- <https://sourceforge.net/projects/mingw-w64/files/> 접속
- GCC 다운로드
  - [MinGW-W64-install.exe](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe)
- 설치 파일 실행
  - 설치 중 Settings 부분에서
    - Architecture 은 **x86_64** 선택
    - Threads 는 **win32** 선택

## GCC 설치 경로 확인
- GCC경로를 설정하기 위해 GCC 설치 위치 파악
  - **C:\Program Files\mingw-w64\x86_64-8.1.0-win32-seh-rt_v6-rev0\mingw64\bin** 위치에 **gcc**, **g++** 실행 파일 확인

## GCC 경로 설정
- 환경 변수 설정 화면 열기
  - 윈도우 키 + R을 눌러 실행 창에서 sysdm.cpl 입력
- 시스템 속성 > 고급 탭 > 환경 변수
- 시스템 변수 > path 선택 > 편집 > 새로 만들기 > GCC설치 경로 입력 > 확인

## GCC 경로 설정 테스트
- 윈도우 키 + R 실행 창에서 cmd 입력
- Command에 gcc –v 를 실행 시켜 아래와 같은 결과 확인
  - 주의: cmd 창 실행전 환경 변수 설정과 관련된 모든 창을 종료해야 함

## VS Code 확장 프로그램
- C/C++ 설치

## VS Code에서 C 컴파일러 설정
- VS Code메뉴 Terminal > Configure default build task 선택
- C/C++: gcc.exe build active file 선택

## VS Code에서 C 컴파일
- 컴파일 하고자 하는 .c 파일에서 Ctrl + shift + b 를 눌러 컴파일

## VS Code에서 exe파일 실행
- 컴파일이 완료화면에서 enter를 눌러 터미널 변경
- 셸은 powershell을 선택하도록 한다
