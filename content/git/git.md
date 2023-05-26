+++
title = "Git"
tags = ["topics", "git"]
categories = ["topics", "git"]
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
```
 git add : untraked 인 파일을 tracked로 변경, 동시에 staged로 변경

 git commit : staged된 파일을 커밋

 git rm : traked인 상태의 파일을 삭제

 git reset HEAD <파일> : 파일 상태를 unstage로 변경

 git commit --amend : 커밋 재작성

 git checkout -- <file> : stage 되지 않은 파일을 되돌리기
 
 git checkout <branch명> : branch로 HEAD를 이동

 git revert <커밋명> : 해당 커밋을 취소

 git reset --hard <이동하려는 이전 커밋> : 특정 커밋으로 이동, 저장이 안되기 때문에 주의해야 함.
```