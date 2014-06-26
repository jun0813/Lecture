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


## 5. 로컬에 NDAP 띄우기
1. NDAP_HOME 설정 (C:\Users\lia\Dropbox) 
2. conf 파일들 복사해왔음. from Joe.Lim (C:\Users\lia\Dropbox\conf)
3. cygwin띄우고 ndap 입력   (=cd /cygdrive/c/Users/lia/Dropbox/00.업무관련/04.KT-NexR/00.NDAP/04.구축/ndap/ndap-webapp)
4. mvn clean tomcat7:run 입력
 
 
-->  html, css 변경사항이 바로 적용됨. 
 
 

# 가이드 작성 관련 설정

## Publican 설치
  
* [퍼블리칸 설치](https://fedorahosted.org/publican/)