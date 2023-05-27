+++
title = "Docker"
tags = ["topics"]
categories = ["topics"]
+++

---
### **docker 개요**
* 가장 대표적인 컨테이너 프로그램, 컨테이너 런타임이라고도 함
* 클라이언트/서버 구조의 프로그램
* 서버 : dockerd, 데몬 프로그램, containerd 사용
* 클라이언트 : docker CLI
* 리눅스 소켓 통신
---
### **docker 설치(wsl Ubuntu)**

#### 사전 작업 : 저장소 설정(도커 설치를 위한 저장소를 설정)
1. apt 패키지 인덱스(소스 리스트) 업데이트하고 필요 패키지 설치
```
sudo apt-get update
sudo apt-get install \
ca-certificates \
curl \
gnupg
```

2. 도커 공식 GPG 키 추가
```
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

3. 저장소 셋업(아래는 하나의 명령)
```
echo \
"deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg]
https://download.docker.com/linux/ubuntu \
"$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### 설치
• apt 패키지 인덱스(소스 리스트) 업데이트
```
sudo apt-get update
```
• 도커 엔진, containerd, 도커 컴포즈 설치
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
---
### **docker 실행**

#### 도커 데몬 실행(root 권한 필요)
* 아래 명령으로 서비스 실행
```
sudo service docker start
```
* 또는 아래 명령으로 백그라운드 서비스로 실행
```
nohup sudo dockerd &
```
* 실행 확인
```
ps -ef|grep dockerd
```

#### 도커 명령 실행
* 버전 확인
```
sudo docker --version
```
* 컨테이너 실행 테스트
```
sudo docker run hello-world
```
---