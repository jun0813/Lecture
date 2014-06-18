# 첫 시간
Sublime Text 2 에디터 사용법.

# 서브라임






요즘 유행하는 에디터. 기본 사용법과 Package에 대해 알아본다.
## 기본 설정
모든 작업은 project를 기초로 일어난다. 그래서 프로젝트 설정을 해야 한다.

* project > add folder to project.. 로 폴더를 추가하면 좌측에 폴더 목록이 생긴다.
* project > save project as... 로 프로젝트 설정파일을 저장한다.

## 기본 단축키
편하지만 생소한 단축키들이 있다. `cmd`는 MAC의 super key이므로 윈도에서는 `window` 키를 누른다.

### 에디팅 (MAC)
* `cmd`+`/` : 한 줄 주석 등록/취소
* `cmd`+`alt`+`/` : 여러 줄 주석 등록/취소. 선택한 영역만 주석화 한다.
* `cmd`+`ctrl`+up :  커서가 있는 라인을 한 줄 올리기
* `cmd`+`ctrl`+down : 커서가 있는 라인을 한 줄 내리기
* `cmd`+`shift`+enter : 커서가 있는 라인 위쪽에 라인 추가
* `cmd`+enter : 커서가 있는 라인의 아래에 라인 추가.
* `cmd`+`shift`+d : 현재 라인을 복사해서 아래에 붙이기. (duplicate)
* `ctrl`+`shift`+k : 현재 라인 삭제 (kill?)
* `ctrl`+`shift`+up/down : **컬럼 선택** 커서를 세로로 여려줄 생성해서 멀티라인 편집이 가능하다.
* `cmd + d`: 선택 영역을 잡고 `cmd + d`를 누르면, 같은 내용을 찾아서 계속 멀티 셀렉팅이 된다. 멀티커서를 이용한 편집에 유용하다.

### 에디팅 (Window)
* `ctrl`+`/` : 한 줄 주석 등록/취소. 여러줄 선택 시, 모두 주석 등록/취소. (단, 줄 중간부터 영역 선택 시 주석 등록은 되나, 취소와 toggle되지 않음.) 
* `ctrl`+`shift`+Up or Down :  커서가 있는 라인을 한 줄 올리기
* `ctrl`+`shift`+enter : 커서가 있는 라인 위쪽에 라인 추가
* `ctrl`+enter : 커서가 있는 라인의 아래에 라인 추가.
* `ctrl`+`shift`+d : 현재 라인을 복사해서 아래에 붙이기. (duplicate)
* `ctrl`+`shift`+k : 현재 라인 삭제 (kill?)
* `ctrl`+`alt`+Up or Down : **컬럼 선택** 커서를 세로로 여려줄 생성해서 멀티라인 편집이 가능하다. (intel 그래픽 카드를 사용하는 경우, 화면 우측 하단의 그래픽 카드 설정 부분에서 "그래픽 옵션 > 바로 가기 키" 를 "사용안함"으로 꺼야한다. 화면 방향 전환 키와 겹침.)
* `ctrl` + d: 선택 영역을 잡고 `ctrl + d`를 누르면, 같은 내용을 찾아서 계속 멀티 셀렉팅이 된다. 멀티커서를 이용한 편집에 유용하다.


### layout
layout은 에디팅 영역을 분할 하는 기능을 말한다. colum, row, grid로 나눌 수 있고, view > layout 에 있다. 이렇게 나뉜 영역을 형태에 관계 없이 `group`이라하며, 좌측 상단에서 시계방향으로 1,2,3,4...란 숫자가 붙는다. group 2는 두번째 column이나 row를 의미한다.

* `cmd` + `alt` + `숫자` : 레이아웃에 컬럼 수 변경, 여러 파일을 비교하면서 볼때 유용하다.
* `ctrl` + `shift` + `숫자` : 현재 커서가 있는 파일을 다른 그룹으로 이동시킨다.
* `ctrl` + `숫자` : 커서를 다른 그룹의 파일로 이동시킨다.
* `cmd` + `숫자` : 현재 그룹에서 tap으로 연 파일들을 옮겨 다닌다.

### 기타 기능
* `cmd` + `p` : 파일명을 치면 프로젝트 안에 있는 파일을 찾아준다.
* `cmd` + `shift` + p : `command palette`를 실행한다. sublime의 기능을 컴맨드 입력으로 실행할 때 사용하며, 주로 `package control` 을 실행할 때 사용한다. sublime의 독특한 기능중 하나로 기능 실행을 메뉴바나 단축키로 하는게 아니라 컴멘드 입력으로 하는 방식이다. 반드시 익숙해져야 한다.
* edit > line > reindent : html의 들여쓰기를 보기좋게 포매팅 한다. 기본 단축키가 없는 기능인다. preferences > key bindings - user 에 다음 내용을 넣으면 `ctrl`+`shift`+`r`를 단축키로 쓸 수 있다.

```
[
  { "keys": ["ctrl+shift+r"], "command": "reindent" , "args": { "single_line": false } }
]
```

## package control 사용법
sublime는 익스텐션(플러그인)을 설치 할 수 있는데 이를 `package`라 부른다. 페키지를 설치, 사용하려면 사전에 `package control`라는 도구를 설치 해야 한다. (package control가 sublime의 기본 기능이 아니라는 말)

### package control 설치
이 과정을 한 번만 하면 된다.

*  [사이트](https://sublime.wbond.net/installation)에 들어가서 sublime text 2의 코드를 copy
* view > show console를 열어서 붙여넣고 enter
* 에디터 하단에 설치 완료가 표시됨
* sublme 재 시작.

### package control 사용
**사용**한다는 말은 package control를 사용해서 package를 설치, 삭제, 열람등의 관리를 한다는 말이다. package control를 사용하려면 `cmd` + `shift` + `p`로  `command palette`를 실행해서 package control이라고 입력한다.

#### 설치
* `cmd` + `shift` + `p`로 command palette를 실행
* `package control`, `package`, `pkcnt` 등을 입력해본다.
*  `package control: install package`를 선택하고 enter
* package control가 설치 가능한 package를 웹에서 가져와서 보여준다.
* 원하는 package를 입력해서 찾는다. (ex, `emmet`) 이미 설치된 package는 검색되지 않는다. 찾은후 enter
* 하단에 상태 영역에 `==`가 깜박인다. 사라지면 설치 완료.
* 원하는 package를 검색할 때는 https://sublime.wbond.net/ 를 사용한다.

## 환경설정
* 환경 설정 변경 (그냥 내꺼)
* 폴터 추가, 프로젝트 저장.

## 유용한 Package 들
### emmet
zen-conding의 새로운 버전. `ul>li.side*4` 같은 식으로 입력 가능. emmet의 강점은 입력 방식보다 추가로 사용할 수 있는 단축키 들이다. 단축키 설명이 이해가 안되면 [readme](https://github.com/sergeche/emmet-sublime)에 있는 단축키 설명 동영상을 참조해야 한다.

* Expand Abbreviation – `Tab` or `Ctrl+E` : emmit 코드를 html 변환
* Interactive “Expand Abbreviation” — `Ctrl+Alt+Enter` : 태그 추가를 인터랙티브하게 할 수 있다.
* Match Tag Pair Outward – `⌃D` (Mac) / Ctrl+, (PC) : 태그 블럭별로 선택을 확장해 나간다.
* Match Tag Pair Inward – `⌃J` / Shift+Ctrl+0 : 태그 블럭별로 선택을 축소해 나간다.
* Go to Matching Pair – `⇧⌃T` / Ctrl+Alt+J : 짝을 이루는 태그로 커서가 이동한다.
* Wrap With Abbreviation — `⌃W` / Shift+Ctrl+G : 커서가 있는 태그를 감싸는 새로운 태그를 만든다.
* Go to Edit Point — `Ctrl+Alt+→` or Ctrl+Alt+← : 여러 태그를 생성 후, 편집포인트로 커서를 이동시켜준다.
* Select Item – `⇧⌘.` or `⇧⌘,` / Shift+Ctrl+. or Shift+Ctrl+, : html 편집시 수정대상이 되는 속성, 값, 태그 등을 순서대로 선택해준다. 마침표는 후방 탐색, 콤마는 전방 탐색
* Toggle Comment — `⇧⌥`/ / Shift+Ctrl+/ : 커서가 있는 태그를 여러줄 주석으로 감쌓준다. (선택할 필요가 없다. )
* Split/Join Tag — `⇧⌘'` / Shift+Ctrl+` : `<p></p>`과 `<p />`사이를 토글한다.
* Remove Tag – `⌘'` / Shift+Ctrl+; : 해당 태그를 제거한다. 맥 단축키는 작은따옴표(')다.
* Update Image Size — `⇧⌃I` / Ctrl+U : 경로가 유효한 `<img>`에서 실제 이미지의 `width`, `height`를 자동으로 추가한다.
* Evaluate Math Expression — `⇧⌘Y` / Shift+Ctrl+Y : 간단한 수식계산을 할 수 있다. (120/5 이런게 계산됨.)
* Reflect CSS Value – `⇧⌘R` / Shift+Ctrl+R : 브라우저 prefix가 있는 css rule들의 값을 한번에 바꿀 수 있다.
* Encode/Decode Image to data:URL – `⇧⌃D` / Ctrl+' : 이미지를 base64 data url로 변환한다.
* Rename Tag – `⇧⌘K` / Shift+Ctrl+' : 태그 명을 쌍으로 한 번에 바꿀 수 있다.
* Increment by 1: `Ctrl+↑` : 숫자의 1의 자리를 증가시킨다.
* Decrement by 1: `Ctrl+↓` : 숫자의 1의 자리를 감소시킨다.
* Increment by 0.1: `Alt+↑` : 숫자의 0.1 자리를 증가시킨다.
* Decrement by 0.1: `Alt+↓` 숫자의 0.1 자리를 감소시킨다.
* Increment by 10: `⌥⌘↑` / Shift+Alt+↑ : 숫자의 10의 자리를 증가시킨다.
* Decrement by 10: `⌥⌘↓` / Shift+Alt+↓ : 숫자의 10의 자리를 감소시킨다.

### EditorConfig
에디터 편집 스타일을 정의하는 설정파일 `.editorconfig`를 서브라임에서 쓸 수 있게 하는 package. editorCofnig에 대해서는 [사이트](http://editorconfig.org/) 참조.

### git
git명령어를 sublime에서 사용할 수 있게 해준다. command palette에서 `git`라고 치면 관련 명령어들이 나온다. git add, git commit, git diff 등이 자주 쓰인다.

### gitgutter
에디터 좌편의 linenumber 옆에 표시되는 아이콘을 gutter라고 하는데, git diff를 표시해주는 gutter를 추가하는 package이다. git를 사용중인 코드에서는 자동으로 뜬다.

### filediffs
파일간 차이점을 비교할 때 사용한다. 다른 pacakge과 달리 에디터에서 오른쪽 마우스 context 메뉴로 접근한다.

### sublimelinter
`lint`란 코드가 적절히 짝여졌는지를 알아보는 절차다. CSS는 [CSSLint](http://csslint.net/)가 있다. 이 패키지를 설치하면 css를 열었을 때 자동으로 오류나 경고가 gutter로 표시된다. command palette에서 `sublimelinter`, `linter`등을 입력하고, `sublimelinter: show error-list`를 선택하면 목록의 내용을 볼 수 있다.

### HTML-CSS-JS Prettify
html, css를 보기 좋게 들여쓰기과 줄바꿈을 해준다. html, css파일에서  command palette를 열고 `prettify`를 입력하고 `HTMLPrettify`를 선택하면 된다.
