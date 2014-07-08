
# The Sass Way

[The Sass Way.com](http://thesassway.com/)는 양질의 sass 정보를 제공하는 사이트.
이를 정리한 내용.

----



## Beginner-Variable name

- semantic variable name. 의미론적 작명
- Adopt useful conventions. `-color`, `-header`같은 작명 규칙.
- Keep a centralized config. 변수는 한 파일에 하고 `@import` 사용.



----



## Beginner-How to structure a Sass project

- [참고할 기본구조](http://thesassway.com/beginner/how-to-structure-a-sass-project)
- `main.scss`는 모든 파일을 합쳐서 css로.
- module, partial, vendor로 나누었음.
- module: css로 output되지 않는 sass를 위한 것들, mixin, function, variable
- partial: css에서 레이아웃별로 나뉘는 구조체, 헤더, 풋터, 메뉴, 컨텐츠 등의 영역별.
- vendor: 수정할 필요없는 다른 사람이 많든 유용한 컴포넌트들, 업데이트가 가능한 것들.
- `base.scss`: partial를 위해 sass 환경을 설정한 기본 sass 파일.



----



## Beginner-Nested selectors: the inception rule

[Original Content](http://thesassway.com/beginner/the-inception-rule)

결론은 **don’t go more than four levels deep.** DOM을 흉내내서 너무 많이 depth를 가져 가지 말라는 말.

### The Problem
[The most common mistake](http://signalvnoise.com/posts/3003-css-taking-control-of-the-cascade)

- CSS는 중첩된 선택자의 규칙을 반복적으로 적어줘야 하지만 sass는 `@extend`를 이용해서 이를 피할 수 있다.
- 하지만 "CSS Selector Nightmare"를 유발할 수 있음.


### CSS Selector Nightmare

- CSS Selector Nightmare란 DOM의 구조화 CSS가 결합도가 높아서 수정이 어려운 것을 말한다.
- 예제는 [Specificity(특정하기)](http://www.htmldog.com/guides/css/intermediate/specificity/)를 걱정할 필요가 없기는 한다. 하지만,
- 렌더링과 사이즈에서 성능 이슈도 있지만, 결정적으로 유지보수가 HTML Element의 생애와 엮인다는게 문제.
- 그러다 보면 inline CSS를 하게 된다.


### Meet The Inception Rule

**don’t go more than four levels deep.**


### Making it fit in the Four or Less principle.

- 이를 실행하려면 context, object, interaction state에 대한 이해가 필요함.
- 별거 아님 site context는 class나 id로 지정하지 않는 1 level로 끝나는 것들.
- page context는 class나 id로 지정하지 않는 개별 화면을 위한 레이아웃 관련. 보통은 2 level.
- class나 id로 지정하는 elements. 실제 js나 html에서 사용할 것들.
- interaction state는 object의 상태가 바뀔 때 사용하는 것. 보통은 4 level를 모두 사용해서 지정.

### Remember

- 더 적은 selector를 쓸 수 없는지 항상 고민해라.
- @extend, mixin을 적극 활용해라.
- html 태그 rule에는 꼭 주석을 달아라.
- HTML 변경이 더 쉬운 방법이면 바꿔라.



----



## Beginner-Getting started with Sass and Compass

### Installation

- [Ruby 설치](http://rubyinstaller.org/)를 먼저 해야함.
- GUI 도구가 있음. [Compass.app](http://compass.handlino.com/), [Scout](http://mhs.github.com/scout-app/)
- `css_parser`도 인스톨 해요. `gem install css_parser`

### Create a test project

```bash
$ compass create project-name
$ cd project-name
$ compass watch
```

`config.rb`를 통해서 프로젝트 설정을 할 수 있다. [설정 참조](http://compass-style.org/help/tutorials/configuration-reference/)

### Write some Sass

- Sass는 두가지 문법을 지원한다. `.sass`, `.scss`
- 원래 `.sass`였으나 혼돈의 여지가 있어서 sass3부터 `.scss`를 지원.
- scss는 **CSS3의 SuperSet**이라서 CSS3의 문법을 그대로 C&P를 해도 그대로 먹음.


----


## Intermediate - Using source mapss with sass


### Generating source maps for Sass

- source map은 sass 3.3부터 지원.
- CSS pre-processor와 [js transpiler](https://github.com/jashkenas/coffeescript/wiki/List-of-languages-that-compile-to-JS)가 유행하면서 코드 디버깅이 어려워졌다.
- 왜냐하면 브라우저에서 적용된 소스(css, js)와 작성한 코드(sass, coffescript)가 달라졌기 때문.
- 그래서 둘을 연결해주는 **source map**이라는 것이 등장.

```bash
$ sass sass/screen.scss:stylesheets/screen.css --sourcemap
```

이렇게 하면 생성된 css하단에 다음 같은 주석이 붙음.

```css
/*# sourceMappingURL=screen.css.map */
```

- 이를 브라우저에서 확인하려면 옵션을 켜야 한다. (브라우저 마다 다름)
- source map에 대한 자세한 내용은 [introduction to javascript source maps](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/)를 참조하라. 모든 source map은 동작이 같다.

----

## Intermediate - Spriting with Sass and Compass
[Original Content](http://thesassway.com/intermediate/spriting-with-sass-and-compass)

### The easy way (compass)

- **Sprite sheet image**란 CSS에서 사용하기 위해서 하나로 합친 이미지를 말한다.
- spriting은 compass가 대박. compass는 이미지를 합쳐서 sprite sheet image를 만들어준다.
- `/images/`는 `config.rb`의 `images_dir`에 지정된 경로가 이미지 root다.
- spriting할 이미지를 명명을 잘 정해서 한 폴더에 넣는다. (**png만 가능하다**)

```
images/
|
`-- toolbar/
    |-- bold.png
    |-- italic.png
    |-- link.png
    |-- code.png
    |-- unordered-list.png
    |-- ordered-list.png
    ...
```

```scss
@import "toolbar/*.png";
```

- `@import`에서 `*.png` 를 만나면 sass는 그 폴더가 sprite sheet대상으로 판단하고, 파일 하나로 만든다.
- 그러면 다음처럼 `all-{folderName}-sprites`란 mixin을 바로 사용가능하다.

```scss
@include all-toolbar-sprites;
```

- css는 이렇게 convert된다.

```css
.toolbar-sprite, .toolbar-bold, .toolbar-italic, .toolbar-link {
  background-image: url('/images/toolbar-s1f1c6cbfd0.png');
  background-repeat: no-repeat;
}

.toolbar-bold {
  background-position: 0 0;
}

.toolbar-italic {
  background-position: 0 -24px;
}

.toolbar-link {
  background-position: 0 -48px;
}
```

- 최종 이미지 경로를 상대경로로 바꾸고 싶다면 `config.rb`에 다음을 추가한다.

```ruby
http_generated_images_path = "../images"
```

```css
.toolbar-sprite, .toolbar-bold, .toolbar-italic, .toolbar-link {
  background-image: url('../images/toolbar-s1f1c6cbfd0.png');
  background-repeat: no-repeat;
}
```

### Controlling class names

- sprite image를 개별 접근할 수 있는 mixin도 제공한다. `{folderName}-sprite()`

```scss
@import "toolbar/*.png";

.bold-icon { @include toolbar-sprite(bold); }
.italic-icon { @include toolbar-sprite(italic); }
.link-icon { @include toolbar-sprite(link); }
```


### Sprite maps

- sprite sheet image를 다루는 다은 방법 `sprite-map()`, `sprite()`

```scss
$icons: sprite-map("toolbar/*.png");

.bold-icon { background: sprite($icons, bold); }
.italic-icon { background: sprite($icons, italic); }
.link-icon { background: sprite($icons, link); }
```

### Controlling spacing

- sprite sheet image에 여백을 줄 수 있다.

```scss
// Using import...
$toolbar-spacing: 5px;
@import "toolbar/*.png";

// Or, if you are using a sprite map...
$icons: sprite-map("toolbar/*.png", $spacing: 5px);
```

### Controlling layout

- sprite 하는 방식을 결정할 수 있다. `{folderName}-layout`
- `{folderName}-layout`의 값. `vertical`, `horizontal`, `diagonal`, `smart`
- 하지만 spacing지정과 함께 `smart`로 지정하면 안된다.

### 추가.

- `sprite-url($icons)` - sprite sheet의 url
- `sprite-position($icons, bold)` - sprite sheet중 bold의 x, y 좌표
- `@include sprite-dimensions($icons, link)` - link의 원래 크기에 기반한 width, height

----

## Understanding placeholder selectors

- sass는 CSS rule별로 코드를 공유할 수 있는 많은 방법을 제공한다.
- mixin도 있고, @extend도 있다.
- sass 3.2에서 여기 placeholder가 추가되었다.


### How extend works

- 일반 `@extend`는 다음처럼 동작한다.

```scss
.icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  @extend .icon;
  /* error specific styles... */
}

.info-icon {
  @extend .icon;
  /* info specific styles... */
}
```

- convert된 css다.

```css
.icon, .error-icon, .info-icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  /* error specific styles... */
}

.info-icon {
  /* info specific styles... */
}
```

- 이 방식의 문제는 사용하지 않는 `.icon`이 생긴다는 것.
- 이를 제거하기 위한 방법으로 나온게 placeholder


### Enter placeholder selectors

- placeholder는 `%`를 사용한다.

```scss
%icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  @extend %icon;
  /* error specific styles... */
}

.info-icon {
  @extend %icon;
  /* info specific styles... */
}
```

- 사용하지 않는 class가 생성되지 않는다.

```css
.error-icon, .info-icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  /* error specific styles... */
}

.info-icon {
  /* info specific styles... */
}
```

### Extend vs. include

- placeholder selector는 파라미터가 없는 mixin(@include로 추가하는)가 유사해 보인다.
- 하지만 convert되는 css가 다르다. mixin은 중복을 생성함.

```scss
@mixin icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

.error-icon {
  @include icon;
  /* error specific styles... */
}

.info-icon {
  @include icon;
  /* info specific styles... */
}
```

```css
.error-icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
  /* error specific styles... */
}

.info-icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
  /* info specific styles... */
}
```

### Limitations

- `@media`와 함께 사용할 때는 제약이 있다.
- 여러 media 간에 공유될 수 없다. 컴파일 에러가 난다.

```scss
%icon {
  transition: background-color ease .2s;
  margin: 0 .5em;
}

@media screen {
  .error-icon {
    @extend %icon;
  }

  .info-icon {
    @extend %icon;
  }
}
```

- 이는 에러가 아니고, 의도된 동작한다. `@extend`는 프로퍼티 중복없이 selector를 추가해서 동작하는데 media를 넘나들며 selector를 합칠 방법이 없다.
- 이를 동작하게 하려면 media query로 placeholder selector를 감쌓면 된다.
- 그러면 이를 @extend한 rule은 해당 media에 속하게 된다.

```scss
@media screen {
  %icon {
    transition: background-color ease .2s;
    margin: 0 .5em;
  }
}

.error-icon {
  @extend %icon;
}

.info-icon {
  @extend %icon;
}
```

- 이렇게 compile된다.

```css
@media screen {
  .error-icon, .info-icon {
    transition: background-color ease .2s;
    margin: 0 .5em;
  }
}
```



----



## Mixins for semi-transparent colors

- sass는 한 색상을 기준으로 다른 색상을 **계산**해 낼 수 있다.
- `darken()`, `saturate()`, `adjust-color()`등을 사용.
- `rgba()`로 반투명 색 생성.

```scss
.button {
  background: rgba(black, 0.5);
}
```

- sass의 `rgba()`는 인자가 두개다. compile하면 인자가 4개인 css `rgba()`가 된다.
- IE 구버전은 이 css `rgba()`을 인식 못하므로 색상을 줘야 한다.

```scss
.button {
  background: #7f7f7f;
  background: rgba(black, 0.5);
}
```

- 이럴때 별도의 **color picker**가 필요한데, `mix()`를 사용하면 필요없다.

```scss
.button {
  background: mix(black, wite, 50%);
  background: rgba(black, 0.5);
}
```

- 이를 배경색에 동적으로 반응하는 mixin으로 만들 수도 있다.

```scss
// @include alpha-background-color(rgba(black, 0.5), white);
@mixin alpha-background-color($color, $background) {
  $percent: alpha($color) * 100%;
  $opaque: opacify($color, 1);
  $solid-color: mix($opaque, $background, $percent);
  background-color: $solid-color;
  background-color: $color;
}
```