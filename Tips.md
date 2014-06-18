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

```
.shadow {
  -moz-box-shadow:    3px 3px 5px 6px #ccc;
  -webkit-box-shadow: 3px 3px 5px 6px #ccc;
  box-shadow:         3px 3px 5px 6px #ccc;
}
```

* 특정 엘리먼트에 shadow 효과 부여. 
* [참고자료 : http://css-tricks.com/snippets/css/css-box-shadow/](http://css-tricks.com/snippets/css/css-box-shadow/)
