+++
title = "Git Hub"
tags = ["topics", "git"]
categories = ["topics", "git"]
+++


## Github

#### 1. Github란?
* git을 기반으로 한 원격 저장소 호스팅 서비스
#### 2. 보안 설정
* github는 2FA(2팩터)인증 설정을 해야 한다. 
* github는 패스워드 입력을 통한 저장소 사용이 금지되어, ssh key를 사용해야 한다.
* ssh key는 ed25519 방식으로 생성할 수 있다.

#### 3. 코드 관리
1. github에서 repository를 생성하고, 로컬 컴퓨터에 clone한다.
2. 로컬에서 작업 내용을 git add 명령어와 git commit 명령어로 커밋을 작성한다.
3. git push를 통해 해당 커밋을 원격 저장소에 반영한다.
4. git pull를 통해 다른 사람의 커밋 내역을 로컬로 가져올 수 있다.

#### 4. 더 나아가서
* 깃허브엔 repository branch마다 protection rule을 적용시킬 수 있다. 
* 이를 이용해서 코드리뷰를 강제하거나, main branch를 보호하는 기능을 수행한다.
* 깃허브엔 organization이라는 것을 생성해, team이나 개인을 초대할 수 있다.

---
## Github.io
* github는 개인 블로그를 작성할 수 있는 기능을 제공한다.
* <유저명>.github.io라는 이름으로 repository를 생성하면, 내부에 index.html을 찾아 호스팅해준다.
* 유저 당 한 개의 블로그만 운영할 수 있다.