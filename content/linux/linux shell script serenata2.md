+++
title = "Linux Shell Script"
tags = ["topics"]
categories = ["topics"]
+++

## Shell Script란?

- Shell : 운영체제의 커널과 사용자 사이를 이어주는 다리 역활을 한다. 즉, 커널이 알아들을 수 있는 프로그래밍 언어.
- Shell Script : Shell에서 사용할 수 있는 명령어가 모인 파일로 첫 번째 줄에 어떤 Shell 인터프리터를 사용할 것인지 명시한다.

## 대표적인 명령행 편집기
1. nano
    - Ubuntu 기본 편집기
    - Ctrl + g : 모든 항목 보기
    - Ctrl + o : 저장
    - Ctrl + x : 종료
    - Ctrl + w : 검색

2. vi/vim
    - 대표적인 Unix용 명령행 편집기
    - 편집모드, 명령모드가 있음
    - esc키로 명령모드로 변경
    - a, i, r, o, O : 편집모드로 변경

## Shell Script 실행
- hello.sh 파일을 실행하고 싶은 경우!
1. Script file 실행 권한 변경
    ```bash
    sudo chmod a+x hello.sh
    ```
2. Shell Script 실행
    ```bash
    # 아래와 같이 총 3가지 방법이 있다
    bash hello.sh
    sh hello.sh
    ./hello.sh #실행 권한 필요
    ```