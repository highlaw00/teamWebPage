+++
title = "Git Hub"
tags = ["topics"]
categories = ["topics"]
+++

--- 
## Git

#### 1. Git이란?
git은 컴퓨터의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템이다.

#### 2. Git 소스 상태
* tracked : 추적 대상(관리 대상)
* untracked : 추적 대상 아님
* git status : 추적 대상인지 확인하는 명령어

#### 3. 관리 대상 상태
* committed : 버전관리에 안전하게 저장됨, snapshot
* staged : 커밋할 대상이라고 표시된 상태
* modified : 파일이 수정되었지만 staged 되지 않음
* tracked 인 파일은 변경을 감지함
* untracked인 파일은 변경을 감지하지 않음
* untracked인 파일이 새로 생긴 것은 감지함

#### 4. git 명령어
* git add : untraked 인 파일을 tracked로 변경, 동시에 staged로 변경
* git commit : staged된 파일을 커밋
* git rm : traked인 상태의 파일을 삭제
* git reset HEAD <파일> : 파일 상태를 unstage로 변경
* git commit --amend : 커밋 재작성
* git checkout -- <file> : stage 되지 않은 파일을 되돌리기
* git checkout <branch명> : branch로 HEAD를 이동
* git revert <커밋명> : 해당 커밋을 취소
* git reset --hard <이동하려는 이전 커밋> : 특정 커밋으로 이동, 저장이 안되기 때문에 주의해야 함.

---
## Github

#### 1. Github란?
git을 기반으로 한 원격 저장소 호스팅 서비스
#### 2. 보안 설정
github는 2FA(2팩터)인증 설정을 해야 한다. 
github는 패스워드 입력을 통한 저장소 사용이 금지되어, ssh key를 사용해야 한다.

#### 3. 코드 관리
1. github에서 repository를 생성하고, 로컬 컴퓨터에 clone한다.
2. 로컬에서 작업 내용을 git add 명령어와 git commit 명령어로 커밋을 작성한다.
3. git push를 통해 해당 커밋을 원격 저장소에 반영한다.
4. git pull를 통해 다른 사람의 커밋 내역을 로컬로 가져올 수 있다.

---
## Github.io
* github는 개인 블로그를 작성할 수 있는 기능을 제공한다.
* <유저명>.github.io라는 이름으로 repository를 생성하면, 내부에 index.html을 찾아 호스팅해준다.
* 유저 당 한 개의 블로그만 운영할 수 있다.