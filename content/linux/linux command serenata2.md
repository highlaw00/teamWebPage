+++
title = "Linux 명렁어"
tags = ["topics"]
categories = ["topics"]
+++

## CLI? GUI?

- CLI : 명령줄 인터페이스
- GUI : 그래픽 사용자 인터페이스

## Linux shell

- 운영체제 상에서 다양한 운영 체제 기능과 서비스를 구현하는 인터페이스를 제공하는 프로그램

## Linux 사용자 계정

- 모든 계정은 숫자로 된 UID 값을 가짐
- root 유저의 UID 0번을 가짐
- 사용자 계정은 /etc/passwd 파일에서 관리됨


## Linux 기본 명령어
- 실행 중인 프로세스 보기

```bash
ps # 프로세서를 보는 명령어
ps -ef | grep python # python이라는 이름의 프로세스의 pid 찾기
kill pid # pid를 가지는 프로세스 강제 종료
```

- 문자열 다루기

```bash
more # 파일의 내용을 한 페이지씩 보여주는 명령어
less # 페이지 보여주는 명령어
cat # 파일 내용 출력
head # [-n 10] -> 맨 앞의 10줄만 보기
tail # [-n 10] -> 맨 뒤의 10줄만 보기
grep # 지정된 문자열이 포함된 행만 표시
```

- 파일의 권한, 권한 수정 명령

```bash
chmod 755 file_name # 111 101 101
chmod o+x file_name # other에게 실행 권한을 줌
chmod a+x file_name # 모든 그룹에게 실행 권한을 줌
```

- ssh keygen

```bash
ssh-keygen -t rsa # RSA 알고리즘으로 키 생성
ssh-keygen -t ed25519 -C "your_mail@address.com" # Github를 위한 keygen

# 개인키 : ~/.ssh/id_rsa
# 공개키 : ~/.ssh/id_rsa_pub
```

- ssh로 원격 시스템에 접속하기
    - ssh란 통신을 암호화 하여 보안을 강화하는 방식
    - 사용방식 : ssh 사용자id@IP -p 포트번호
    - 만약 포트를 특정하지 않으면 22번 포트로 ssh 접속 요청
    - 만약 사용자id를 특정하지 않으면 현재 시스템 사용자id로 접속을 요청
    
```bash
ssh edu@195.117.50.9 -p 10022 # id : edu, ip : 195.117.50.9, port : 10022
```


- 기타

```bash
mkdir # 디렉토리 만들기
rmdir # 디렉토리 지우기
touch # 빈 파일을 만들기
which # 경로에 있는 파일 찾기
```