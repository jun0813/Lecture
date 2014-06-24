# AngularJS 개발환경설정

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
