# 개발환경설정

## 1. JDK 설치

### 다운로드
* [최신버전 JDK 다운로드 & 설치(2014.06.24 현재는 1.6)](http://www.oracle.com/technetwork/java/javasebusiness/downloads/java-archive-downloads-javase6-419409.html#jdk-6u45-oth-JPR)

### 설치
* 더블클릭해서 설치

### 환경변수 설정

* [JAVA_HOME, PATH 설정](http://h5bak.tistory.com/91)

## 2. Maven 설치

* [메이븐이란?](http://scolor.tistory.com/19)

### 다운로드
* [최신버전 다운로드 (2014.06.24 현재는 apache-maven-3.2.1-bin.zip](http://apache.tt.co.kr/maven/maven-3/3.2.1/binaries/apache-maven-3.2.1-bin.zip)

### 설치
apache-maven-3.2.1 압축 풀고, 폴더를 C드라이브 아래 바로 붙여넣고...

### 환경변수 설정             

* [MAVEN_HOME, PATH 설정](http://kyungseo.pe.kr/archives/513)

### MAVEN 설정

* 내 PC에 설정하는 경우 : `${user.home}/.m2` 폴더에 `settings.xml` 파일 생성.
* settings.xml 값 설정(메일로 받았음. "settings.xml 설정" 참고.)
* [아파치 메이븐 가이드 참고](http://maven.apache.org/settings.html)

### 빌드 테스트

* command에서 `mvn clean DskipTests install` 입력하여 실행해보면 됨.
* 지금 우리 프로젝트는.. 최초 빌드 한 30분 걸림;;; 

## 3. node.js 설치

### 다운로드 & 설치
* [최신버전 다운로드 : `install` 클릭 ](http://www.nodejs.org/)

### 설치 확인
* command에서 `node` 입력하여 실행해보면 됨.

## 4. 앤답 설치하기
* webapp만 로컬에서 구현할꺼라서, core 붙을 곳을 설정해둬야함. 
* 클라우드 vm으로 하나 설정했음.  ( [lia04](http://wiki.nexrcorp.com/display/BD/Ucloud+VM+list) )
* mysql root 비번 기본값이 사용하던 것과 다름. (=)

### 앤답 3.1.0 설치하기                
* [설치 가이드 참조](https://github.com/nexr/ndap-playbooks/tree/ndap-3.1)

### 재설치시 (설치 가이드 상에서 제목으로 검색)
1. "삭제"
```
ansible-playbook -i hosts uninstall.yml
```
2. "업그레이드"
```
ansible-playbook -i hosts upgrade.yml
```
3. "전체 과정" 대로 새로 설치
* 내가 수정해놓은 설정파일이 그대로 유지됨. (hosts, var_groups 파일들..)

### ACL True가 먹지 않으면....
```
service ndap-management restart
```

## DB 접근권한 부여
* "mysql" 권한부여(외부IP에서 접근가능하도록 처리)
* 외부접근 권한이 없기때문에, ssh로 해당 서버에 접속한 후에 mysql 실행하여 외부접속 권한을 부여해야 함.
* 루트로 들어가서 앤답에 앤답처리.
```
mysql -u루트 -p루트비밀번호
grant all privileges on *.* to DB아이디@'%' identified by 'DB패스워드'
```


## 5. 로컬에 NDAP 띄우기
### 사전작업
1. NDAP_HOME 설정 (C:\Users\lia\Dropbox) 
2. conf 파일들 복사해왔음. from Joe.Lim (C:\Users\lia\Dropbox\conf)
3. bash_profile 파일에 단축명령어 미리 설정(쓰기편하게...)
```
lia@lia-PC ~ $ vi .bash_profile
alias ndap="cd /cygdrive/c/Users/lia/Dropbox/.../04.구축/ndap/ndap-webapp"
lia@lia-PC ~ $ source .bash_profile
```

### 로컬에 띄우려면?
1. cygwin띄우고 ndap 입력
2. mvn clean tomcat7:run 입력
 
 
-->  html, css 변경사항이 바로 적용됨. 
 
 

# 가이드 작성 관련 설정

## Publican 설치
  
* [퍼블리칸 설치](https://fedorahosted.org/publican/)