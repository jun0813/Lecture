# angular todo MVC 템플릿 다운받기!

- 참고 사이트
[ToDo MVC](http://todomvc.com/)


- 소스 다운로드
[github 소스](https://github.com/tastejs/todomvc/tree/master/architecture-examples/angularjs)


# 소스 직접 짜보기.

- `/Users/lia/Projects/k2amj2ik.github.io/angular/todo-template/` 경로에 샘플소스 받아놨음
- index.html에서 ng-app, ng-view 설정된 것 확인.
- `<script src="https://code.angularjs.org/1.2.9/angular-route.min.js"></script>` 는 view(url 과 view는 1:1 관계)가 여러개일때 필요한 모듈이다.

## 간단하게 서버 띄우기
- 서버를 띄워야!! ajax 호출을 할 수 있다.
1. terminal에서 해당 루트로 설정할 경로로 이동한다.

```
~/Projects/k2amj2ik.github.io/angular/todo-template
```

2. 파이썬에서 제공하는 간단한 웹서버를 원하는 포트에 띄운다. (alias로 설정해놓으면 편함!!!)

```
python -m SimpleHTTPServer 8000
```

## 라우팅 설정하기.

- $모듈명 `$route` 에 환경설정용 모듈명인 `Provider`를 붙여서 `$routeProvider` 라고 `app.config()` 함수에 넘기면 환경설정이 가능함.
- 각 template은 view를 지정한다. 특정 url을 지정할 수 있다. (url 지정 시 `templateUrl` 로 설정)
- 경우에 따라 url이 달라진다면, template값에 함수를 지정할 수 있다.
- 그 template을 컨트롤하기 위해서 controller를 별도 지정할 수 있다.

## 화면코딩하기.

- view(=template)와 controller는 `$scope`을 공유한다. (따라서, 어느쪽이 수정되던 바로 반영됨. = 2 way binding)


### controller안의 변수, 또는 메소드를 사용하는 방법
- variable이 없어도, view에서 ng-model선언하는 순간, 해당 scope에 그 변수가 생긴다.  


#### `{{varName}}`
- angular expression으로 표현한다.
- 해당 view가 어차피 한 $scope에만 바인딩 되어있기 때문에, 앞에 `$scope.`을 표시하지 않는다.  

### view에서 element의 값을 controller로 넘겨주는 방법
- `ng-model` 을 element에 속성으로 넣어주면 해당 $scope의 controller로 값을 넘겨준다.(실시간으로...)
- ex) 체크박스가 unchecked면 false, checked면 true가 넘어간다.(angular에서 사전 정의 되어있음)

### ngCloak
- view의 angular 코드를 실제 소스로 치환하는 과정에서 앞의 코드 잔상이 노출될 수 있는데, 그걸 방지하는 코드. (자세한 내용은 좀 더 찾아봐야 할 듯)

### ngRepeat
- for문의 추상화 된 기능.
```
<li ng-repeat="todo in todos" class="{{todo.completed}}">
    {{$index}} | {{todo.completed}}, {{todo.title}}. {{newTodo}}
</li>
```
- `아이템 in 컬렉션` 으로 표현. 아이템은 임의의 명칭을 아무렇게나 사용.
- for문을 돌릴 수 있다면 `컬렉션`이라고 부른다.(js에서는...)

```
<li ng-repeat="todo in todos | filter:statusFilter track by $index" ng-class="{completed: todo.completed, editing: todo == editedTodo}">
  <div class="view">
    <input class="toggle" type="checkbox" ng-model="todo.completed">
    <label ng-dblclick="editTodo(todo)">{{todo.title}}</label>
    <button class="destroy" ng-click="removeTodo(todo)"></button>
  </div>
  <form ng-submit="doneEditing(todo)">
    <input class="edit" ng-trim="false" ng-model="todo.title" todo-escape="revertEditing(todo)" ng-blur="doneEditing(todo)" todo-focus="todo == editedTodo">
  </form>
</li>
```
- `track by 기준값`으로 repeat 아이템 구별기준을 지정할 수 있다. (값이 완전히 동일한 경우, 아이템을 구분하지 못하는 angular 특성때문에..)
- `filter:속성` 요렇게하면, 아이템의 값을 속성값과 비교하여 같을 때만 노출한다.
- filter조건으로 목록 노출기준으로 변경할 수 있는데, status로 비교하여, `전체`, `완료`, `미완료` 이런식의 목록 구분이 가능해진다.
- `ng-class`는 `class`명을 동적으로 변경하기 위해서 기본 제공되는 directive(지시자)이다. 반드시 객체`{}`를 넘겨야 한다
 ```
 <li ng-class="{completed: todo.completed}">
 ```
 - `ng-class={css클래스명:그 클래스가 적용될 조건}`
 - todo.completed값이 true or false라서, true인 경우에만 completed 클래스가 노출된다.
 
 


# 명칭

- Object : app.  
- method 호출 : .config() 
- function : config()
- arguement : (요거!!)
- property : .word




# mock server 설정하기

- [node 깔고](http://www.nodejs.org/)!!
  --> 노드 다운로드 받아서 깔았어~~
- [node easy mock](https://github.com/CyberAgent/node-easymock) 설치
```
sudo npm install -g easymock
```
- json 파일 만들기
  --> 프로젝트 폴더 하위에 "mock" 폴더 하나만들고...
  --> 명명규칙 : api명_http메서드유형.json 만든다.
  
- 내용은 객체로..넣는데...요거 알아서 찾아봐...
```
{
    "data" : [
        {
            "completed": false,
            "title": "숙제1"
        },
        {
            "completed": true,
            "title": "숙제2"
        },
        {
            "completed": true,
            "title": "숙제3"
        }
    ]
}
```
- easymock실행 ('실행'한 폴더 위치가 api root가 됨.)
```
$ easymock
```
- 그러면... 요런 주소 사용가능... http://localhost:3000/todos 
  --> 바로 json이 호출됨.

- 위 형태는 리스트 형태구... 만약 리스트중 하나를 조회하는 형태를 하려면...
  --> 현재파일 : mock/todos_GET.json : http://localhost:3000/todos
  --> 추가파일 : mock/todos/123_GET.json : http://localhost:3000/todos/123
  
## CORS (JS 도메인 문제...) 해결하려면... config 추가 필요.

- [복사할 내용](https://github.com/CyberAgent/node-easymock#configjson)

# mockup api 접속하기

- $resource 를 설정하고..
  --> app.js, index.html 각각 설정. 
```
controller: function($scope, $resource){
var todoApi = $resource('http://localhost:3000/todos');
        
```

- 쓸려면 담어!
```
//성공했을 때..
            function success(response){
                $scope.todos = response.data;
            }
//실패했을 때..
            function fail(reason){
                throw reason.messsage;
            }

```

- $resource를 가져와!
```
todoApi.get(success,fail);
```
