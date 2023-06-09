+++
title = "Docker Network"
tags = ["topics"]
categories = ["topics"]
+++

---
### **docker 네트워크**

#### docker 네트워크 구성
* 도커 엔진이 시작될 때 docker0 네트워크 어댑터
* 생성컨테이너가 시작될 때마다 veth 가상 네트워크 어댑터 생성

#### 라우팅
* 컨테이너 -> 외부 네트워크(인터넷)
    - 컨테이너 네트워크 WSL의 Hyper-V의 버추얼 스위치를 통하여 보통의 공유기와 같이 외부 네트워크와 통신

* 컨테이너 -> wsl 네트워크
    - wsl의 eth 네트워크로 연결
    - wsl의 docker0 네트워크로 연결
    - ex: 192.168.0.228, 172.17.0.1

* 컨테이너 -> host(Windows) 네트워크
    - Windows의 LAN 어댑터 네트워크로 연결
    - ex: 192.168.0.228

* 호스트(Windows) -> 컨테이너
    - 호스트에서 컨테이너로 접속할 수 있는 경로가 없으므로 연결할 수 없음
    - 컨테이너의 포트를 매핑하여 호스트(WSL)의 포트로 노출시켜야 함

* 외부(인터넷) -> 컨테이너
    - 컨테이너의 포트를 매핑하여 WSL의 포트로 노출시키고 노출된 WSL 포트를 윈도우에서 포워딩 설정
    ```
    netsh interface portproxy add v4tov4 listenport=<포트번호> listenaddress=0.0.0.0 connectport= <포트번호> \
    connectaddress=<WSL의 ip address>
    ```
    - 설정 보기
    ```
    netsh interface portproxy show v4tov4
    ```
    - 포트 포워딩 제거하기
    ```
    netsh interface portproxy delete v4tov4 listenport=<포트 번호> listenaddress=0.0.0.0
    ```
---
### **도커의 영구 스토리지**

#### 컨테이너의 영구 스토리지 필요성과 사용 방법
* 도커 컨테이너의 저장소는 외부와 단절되어 있으며 컨테이너가 삭제될 때 같이 삭제됨
* 컨테이너가 삭제되어도 데이터를 보관할 수 있는 영구 저장소(permanent storage) 필요
* 컨테이너 외부와 데이터를 주고 받기위해서도 외부에서 접근 가능한 저장소 필요
* 도커에서는 다음과 같은 2가지 영구 저장소 사용 방식을 제공
    - 도커 볼륨(Volume)
    - 바인드 마운트(Bind Mount)
* 도커는 볼륨 사용을 권장하나 본 과정에서는 간편한 바인드 마운트 방법을 사용

#### 바인드 마운트 방법
* docker run 명령에서 -v 옵션을 사용
```
    ex: docker run -v <host dir>:<container dir>
```
---