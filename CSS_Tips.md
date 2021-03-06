## 문서 기본 검색
* `MDN ---` 엠디엔을 붙여서 검색하면 mozila development network 사이트로 이동하는데, 여기 설명 작살임!!!!



## 웹폰트

#### IE6~8 호환을 제공해야 하는 경우
```
@font-face{
    font-family:"ng";
    src:url('/fonts/NanumGothic.eot');
    src:url('/fonts/NanumGothic.eot?#iefix') format('embedded-opentype'),
    url('/fonts/NanumGothic.woff') format('woff'),
    url('/fonts/NanumGothic.ttf') format('truetype');
    url('/fonts/NanumGothic.svg#NanumGothic') format('svg')
    src:local(※), url('/fonts/NanumGothic.woff') format('woff');
}
body{font-family:나눔고딕, NanumGothic, ng}
```
#### IE9 이상 지원 시
```
@font-face {
        font-family: ng;
        src: url(/fonts/NanumGothic.woff);
}
body{font-family:ng}
```
                                             
* 서버의 웹폰트를 다운로드 받게설정하는 방법. 첫 다운로드시 로딩 속도 문제가 발생. 
* 차선책으로는 "[모빌리스 웹폰트](http://api.mobilis.co.kr/webfonts/)"를 이용하는 방법이 있음. (단, 상용으로 사용 시 비용 발생)


#### 웹폰트에 대한 이해
* [CSS3 @font-face Rule](http://www.w3schools.com/cssref/css3_pr_font-face_rule.asp)
* [웹 폰트 문제 해결. @font-face troubleshooting. src:local(※)설명 포함](http://naradesign.net/wp/2012/06/19/1830/)
* [[CSS] 웹폰트 적용하는 방법](http://www.freezner.com/archives/215)
* [@font-face 로 한글폰트 맑은고딕 적용하기](http://www.1efthander.com/fontface-malgungothic-apply/)
* [나눔폰트는 무료 라이센스임](http://hangeul.naver.com/download.nhn)

#### 폰트 다운로드
* [IE6~8 전용 eot 포멧](http://weaverloft.com/inc/file/NanumGothic.eot)
* [권장 포멧 woff](http://weaverloft.com/inc/file/NanumGothic.woff)






## :before, :after

```
a:after {
    content: "("attr(href)")";
}
```

* 특정 엘리먼트 앞/뒤에 원하는 컨텐츠를 추가할 수 있다. 
* [참고자료 : http://www.slideshare.net/yakuyaku/ss-34832795](http://www.slideshare.net/yakuyaku/ss-34832795)


## box-sizing

```
box-sizing: border-box;
```

* border 두께 상관없이 상자 크기 고정. (상자 안쪽으로 border가 생기도록..) 
* [참고자료 : http://ko.learnlayout.com/box-sizing.html](http://ko.learnlayout.com/box-sizing.html)



## box-shadow

### 브라우저 호환을 고려해야 한다면...

```
.shadow {
  -moz-box-shadow:    3px 3px 5px 6px #ccc;
  -webkit-box-shadow: 3px 3px 5px 6px #ccc;
  box-shadow:         3px 3px 5px 6px #ccc;
}
```

### IE9이상...

```
box-shadow: 0 1px 2px rgba(0,0,0,0.075);
  
```

* 특정 엘리먼트에 shadow 효과 부여. 
* 값 순서 : inset여부, 너비horizontal,  높이vertical, 블러blur, 퍼짐spread distance, 색상color
* 콤마로 구분하여 입력하면 여러 shadow 적용 가능
* [참고자료 : http://www.slideshare.net/headvoy/css3-boxshadow](http://www.slideshare.net/headvoy/css3-boxshadow)


## CSS Selector

```
input[type="text"] {
    margin-left: 4px;
}
```

![이미지](images/selector_1.png)
![이미지](images/selector_2.png)

* [CSS 선택자(Selector)의 종류 및 간단한 효과주기](http://www.clearboth.org/css3_1_by_isdn386/)
