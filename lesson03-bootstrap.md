# Bootstrap

사이트 메뉴별로 주요 포인트만 집는다.
[국문](http://bootstrapk.com/BS3/css), [영문](http://getbootstrap.com/getting-started/)

# Getting Started
## 관련 용어
compiled, miified, bower, cdn, less, sass, recess, Glyphicons, polyfill, [typeahead](http://twitter.github.io/typeahead.js/examples/)
[Bootply.com](http://www.bootply.com/), customize, data-

## 하위 호환
생각보다 class 차이가 많이 남. 2.x와 주의 해서 사용해야 할 듯.

## 미디어 쿼리 분기 width 값과 prefix
- 768px, 992px, 1200px
- xs, sm, lg

## IE 호환성 모드

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```

`IE=edge`는 최신 IE기준으로 렌더링 하라는 뜻. W3 Validator에서는 오류가 나지만 무시할 것.

http://stackoverflow.com/questions/6771258/whats-the-difference-if-meta-http-equiv-x-ua-compatible-content-ie-edge-e

## 접근성

```html
<a href="#content" class="sr-only">콘텐츠로 바로가기</a>
```

[ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)

[aria-labelledby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute)

[role]((https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques))

, aria-hidden, aria-describedby

 ----

# CSS
## CSS 초기화

[normalize](http://necolas.github.io/normalize.css/) 크로스브라우징을 위한 reset.css


## .container
이 class는 중첩을 지원하지 않는다.

## Grid
화면 크기에 따른 with값에 대한 이해.

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
