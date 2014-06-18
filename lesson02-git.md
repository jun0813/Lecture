# Git and Github
## git이란?
[git}(http://www.git-scm.com/)은 분산 버전 관리 시스템(**DVCS, distributed version control system**). 쉽게 말해 무한 undo가 가능한 text 파일(paln text) 관리 도구. 

**사이트에는 쉽다고 되어있지만 전혀 쉽지 않음.**

### 특징
* git 로컬 도구다. (저장소가 로컬에 있다)
* 빠르로, 용량적고, 편하고, 대중소 모든 프로젝트에 적합. 

## git 작동 원리
* 모든 기록은 `.git/` 에 된다. 
* repository를 구성하는 object : blob, tree, pointer, 
* revision number(hash id, checksum) `git hash-object
* ![](http://i.stack.imgur.com/UpJvH.png)
* commit (snapshot) `
* 단계 :  repository, staging area, working directory
* 명령어 :  commit, add, checkout
* ![](http://assets.osteele.com/images/2008/git-workflow.png)
* 상태 : modified, staged, committed 
* ![](http://www.kobashicomputing.com/sites/kobashicomputing.com/files/images/development/git-file-phases.jpg)

### pointer
* branch(master), tag, head
* 모든 변경은 blob 으로 저장된다. 

### remote
* origin, upstream, fork

### git 명령어
init, status, add, commit, checkout, branch, push, fetch, merge, rebase, pull, tag, log, 

## 작업흐름
### repository 생성
git init
### 코드 저장
status, commit, checkout, head
### 로그 조회
log
### 되돌리기
checout, 
### branch
merge, rebase
### 리모드 저장소, 공유
patch, push, pull, pull-request, .git/
### 태깅
* 변하지 않는 pointer
* push 가능
* github에서는 압축 파일로 관리됨

### 브랜치
merge, rebase의 차이. 
fast-forward

## Github

### github 메뉴 설명
* **home**
* **Repostory home**
	* https://github.com/{user id}/{repository}.git
	* 파일 생성, 편집
	* 변경 조회
	* 커뮤니케이션
	* 설정

### Issue
* close, fix, resolve의 과거, 현재, 3인칭 단수형 [link](https://help.github.com/articles/closing-issues-via-commit-messages)

### wiki
* [GFM](https://help.github.com/articles/github-flavored-markdown)
* https://github.com/{user id}/{repository}.wiki.git


### gh-pages
* 종류 - user page, repository page
	* user page : zziuni.github.io:master branch
	* repository : repo:gh-pages branch
* 수동 - gh-pages 브랜치에 코딩올리기  or jekyll
* 자동 - 홈페이지 - 관리 메뉴 사용. readme.md 사용
* 접근 방법
* https://help.github.com/categories/20/articles

### Gist
* 프로포타이핑, 공유, snippet
* revisions 관리됨. 
* 코드 붙이기 
* https://app.gistboxapp.com/
* sublime package [gist](https://sublime.wbond.net/packages/Gist) 토큰 생성 필요.
