# Sass

- [사이트](sass-lang.com)
- 이하는 [가이드 문서](http://www.sass-lang.com/guide)를 정리한 내용.

## Pre-Processing
- Sass는 변수, 중첩, mixin, 상속등의 css에 없는 기능들을 제공함.
- Sass로 코딩하고 이를 css로 변환해서 사용함.

## Variables

- 변수(variable)이란 stylesheet에서 재사용할 정보를 저장하는 방법 or 장소.
- 생상, 폰트 등의 모든 CSS 값을 저장할 수 있다.
- `$`기호를 이용해 변수를 만든다.

```sass
$font-stack:    Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color
```

변수 값을 체우고 CSS로 바꾸면 이렇게 된다.

```css
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
```

## Nesting
- CSS는 HTML처럼 중첩 구조로 코딩할 수 없지만 Sass는 가능하다.

```sass
nav
  ul
    margin: 0
    padding: 0
    list-style: none

  li
    display: inline-block

  a
    display: block
    padding: 6px 12px
    text-decoration: none
```

- 이방식의 장점은 가독성. CSS로 변환하면 다음과 같다.

```css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}

nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

## Partials

- partial sass files이란 다른 Sass파일이 include할 수 있는 CSS 조각파일을 말한다.
- css를 모듈화 하고 유지보수를 용의하게 하는 방법.
- `_partial.scss`처럼 `_`로 시작하는 파일.
- Sass는 `_`로 시작하는 파일이 partial file임을 알고 CSS로 만들지 않는다.
- `@import`로 partial file를 사용한다.

## Import

- css도 `@import`아 있지만 http request가 발생한다.
- `@import` 같은걸 지시자(directive)라 함.
- sass는 미리 합쳐서 단일 css파일로 제공
- `@import 'reset'` 처럼 언더스코어와 확장자는 붙일 필요없다.

```scss
// _reset.scss

html,
body,
ul,
ol {
   margin: 0;
  padding: 0;
}
/* base.scss */

@import 'reset';

body {
  font-size: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
```

요롷게 CSS로 바뀜

```css
html, body, ul, ol {
  margin: 0;
  padding: 0;
}

body {
  background-color: #efefef;
  font-size: 100% Helvetica, sans-serif;
}
```


## Mixins

- CSS는 지루하게 반복되는 경향이 있음.
- Mixin은 재 사용할 CSS 덩어리를 정의한 것.
- 유연성을 위해 값을 넘길 수도 있음.
- 다음 예제는 vendor prefixs를 붙인 `border-radius`

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

- 지시자 `@mixin`과 사용할 이름 `border-radius`을 적어서 정의한다.
- `$radius`인자를 정의해서 사용할 값을 그때그때 정의할 수 있게 했다.
- 사용할 때는 `@include`를 쓴다.
- 생성되는 CSS

```css
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

## Extend/Inheritance

- `@extend`는 CSS set를 공유시켜준다.

```scss
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}

.warning {
  @extend .message;
  border-color: yellow;
}
```

- 위 코드는 `.message`의 CSS속성을 가져와서 `.success` 등에 적용한다.
- 이를 이용하면 HTML에 여러 class name을 적지 않아도 된다.

```javascript
    var test = 'test';
```


```css
.message, .success, .error, .warning {
  border: 1px solid #cccccc;
  padding: 10px;
  color: #333;
}

.success {
  border-color: green;
}

.error {
  border-color: red;
}

.warning {
  border-color: yellow;
}
```

## Operators

- 기본적인 수학 연산자를 지원한다. `+`, `-`, `*`, `/`, `%`

```scss
.container { width: 100%; }

article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complimentary"] {
  float: right;
  width: 300px / 960px * 100%;
}
```

- 960px기반의 메뉴와 컨텐츠 메뉴를 구분했음.

- px과 %같이 써도 충돌하지 않음.

```css
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 62.5%;
}

aside[role="complimentary"] {
  float: right;
  width: 31.25%;
}
```

## function (추가)

- [Built-in functioins](http://sass-lang.com/documentation/Sass/Script/Functions.html)
- [활용예 lightness()](http://thesassway.com/intermediate/dynamically-change-text-color-based-on-its-background-with-sass)
