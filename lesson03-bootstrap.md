# Bootstrap

사이트 메뉴별로 주요 포인트만 집는다.
[국문](http://bootstrapk.com/BS3/css), [영문](http://getbootstrap.com/getting-started/)

# Getting Started
## 관련 용어
* compiled : 개발시 분기해서 작업한 파일을 하나로 합하는 작업.
* miified : 엔터, 주석, 공백 없애서 소스 최소화
* bower : Yum같은 패키징 프로그램. javascript(브라우저에서 작동하는) 관련 어플리케이션을 받는데 주로 사용. node.js가 사전 설치되어있어야 함. 
* CDN : 유명한 CDN 사이트에 해당 css 또는 js를 걸어서 제공하면, 클라이언트가 이미 받았을 확률이 높기 때문에 캐시를 유도하여 성능향상 및 트래픽 절약이 가능해짐. 
* less, sass : CSS preprocessor. 부트스트랩은 Sass로 앞으로 간다고 함.
* recess : twitter에서 제공하는 CSS, Less 용 linter (=hinter) [well-formed 기준 보기](http://twitter.github.io/recess/) 
* Glyphicons : 폰트에 글꼴지정해서 이미지를 표현하는거. [Graphicons halflings](http://www.graphicons.com)
* polyfill : IE6,7등... 하위 버전 호환을 맞추기 위해 뭔가 하는걸... `polyfill` 이라 한다.
* [typeahead](http://twitter.github.io/typeahead.js/examples/) : input 에서 자동완성 레이어 기능을 말함. twitter에서 아예 라이브러리로 출시했음. 
* [Bootply.com](http://www.bootply.com/) : bootstrap 테스트 서비스
* [Bootstrap customize](http://getbootstrap.com/customize) : bootstrap 에서 less, sass의 각종 변수값을 변경하여 전체 소스를 다시 받을수있게 기능을 제공한다. 
* data- : bootstrap에서 제공하는 javascript로 만들어진 기능들... 을 구현하기 위해서 임의로 추가한 attribute들의 naming rule(표준)
* CSS media query : 보이는 매체가 printer, screen, screen-reader.. 등..각각에 맞게 조건을 지정할수있게 설정하는 css rule (.aaa>bbb cc.dd 식으로 표현한 걸 css rule이라 함.)
```
@media(max-width:767px){}
@media(min-width:768px){}
@media(min-width:992px){}
@media(min-width:1200px){}
```

## 하위 호환
* 생각보다 class 차이가 많이 남. 2.x와 주의 해서 사용해야 할 듯. 
*  **회사꺼는 2.x 임!!!!**

## 미디어 쿼리 분기 width 값과 prefix
- 768px, 992px, 1200px
- xs, sm, lg

## IE 호환성 모드

* IE=edge로 하면, browser에서 `호환성 보기`를 체크해도 최신버전으로 렌더링함.
* `IE=edge`는 최신 IE기준으로 렌더링 하라는 뜻. W3 Validator에서는 오류가 나지만 무시할 것. 
* [관련 설명](http://stackoverflow.com/questions/6771258/whats-the-difference-if-meta-http-equiv-x-ua-compatible-content-ie-edge-e)

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```




## 접근성 (장애인에 대한 걸 의미함)

```html
<a href="#content" class="sr-only">콘텐츠로 바로가기</a>
```

[ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)

[aria-labelledby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute)

[role]((https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques))

, aria-hidden, aria-describedby

 ----

# CSS

## 반응형 이미지
* 이미지는 고정 사이즈가 기본임. `img-responsive` 클래스를 지정해야 width 100%, height auto로 지정됨.
. 
## CSS 초기화
[normalize.css](http://necolas.github.io/normalize.css/)를 탑재하여, 각종 엘리먼트의 기본 style 값을 설정해줬음. 제일 위에 요거 놓고 css 시작해야 함. 


## .container
* media query의 기준 단위가 됨.
* 이 class는 중첩을 지원하지 않는다.

## Grid
* 테이블과 가장 큰 차이는, 가로폭에 따라서 각 개체의 위치가 자유롭게 바뀐다는 것.
* 화면 크기에 따른 with값에 대한 이해.

[clearfix](http://ko.learnlayout.com/clearfix.html)

media query에서 `max-width`로 더 한정할 수 있음.

sass를 할 거므로 less는 path

## Less 변수

 LESS 변수(@font-size-base 와 @line-height-base)는 customize때 사용.

##  코드

```
<code> <address> <abbr> <blockquote>
```

## 폼

input은 container의 100% width

### input의 종류
[MDN input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Input)


## 핼퍼 클래스

[영문](http://getbootstrap.com/css/#helper-classes)을 봐야 함

## 반응형 핼퍼 클래스

----

# 콤포넌트

## Glyphicons
은 폰트.

## 드롭다운

- `data-toggle`을 제외하면 그냥 UI만.
- js와 `data`둘 중의 한 방법으로 사용.

## 버튼 그룹
- 버튼 툴바는 페이지네이션으로 사용됨.


----

#자바스크립트
## 모달
ARIA 관련
## 스크롤스파
