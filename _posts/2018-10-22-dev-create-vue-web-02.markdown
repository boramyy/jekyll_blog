---
layout: post
title: "Vue로 만든 Todo페이지 gh-pages에 배포하기"
excerpt: This post is about cats
date: 2018-10-24
categories: development
tags: vue javascript github gh-pages
published: false
---

### npm run build

`npm run build`를 하면 `dist`폴더가 생깁니다. <br/>
`dist`폴더 하위에 js, css 그리고 index.html, favicon.ico 요롷게 생긴다.

### npm run build로 생성된 dist 폴더구조
``` shell
dist 
  └ css
    └ app.~~~.css
  └ js
    ├ app.~~~.js
    ├ app.~~~.js.map
    ├ chunk-vendors.~~~.js
    └ chunk-vendors.~~~.js.map
  ├ favicon.ico
  └ index.html
```


index.html 내부 `link`태그의 `href`속성과 `script`태그의 `src` 속성에 /js 또는 /css 로 시작하는 주소를 자신의 repository 이름으로 시작해야 합니다!

/v-todo/js... , /v-todo/css...

``` html 
<link href=/v-todo/css/app.dc9a26ca.css rel=preload as=style>
<link href=/v-todo/js/app.a331c5f4.js rel=preload as=script>
<link href=/v-todo/js/chunk-vendors.e622eab0.js rel=preload as=script>
<link href=/v-todo/css/app.dc9a26ca.css rel=stylesheet>
.
.
.
<script src=/v-todo/js/chunk-vendors.e622eab0.js> </script> <script src=/v-todo/js/app.a331c5f4.js> </script> </body> </html>
```

{% highlight html linenos %}
<link href=/v-todo/js/app.a331c5f4.js rel=preload as=script>
<link href=/v-todo/js/chunk-vendors.e622eab0.js rel=preload as=script>
<link href=/v-todo/css/app.dc9a26ca.css rel=stylesheet>
{% endhighlight %}

그리고 `"file":"` 로 전체 검색을 하면, `.js.map` 파일 내부에서 참조하는 파일 주소가 작성되어 있는데 그것 역시 자신의 레포 주소로 시작하면 됩니다!

<img src="/assets/img/vue02-search.png" alt="Search Example" title="Search Example" width="520">

``` javascript
js/~~ // 이렇게 되어있는 주소들을
v-todo/js // 이렇게 자신의 repository 이름으로 시작하게 합니다.
```

``` javascript
/js/~~ // 슬래시가 있던 친구들은 그대로 슬래시를 처음에 두세요!
/v-todo/js // 이렇게요!
```

### gh-pages 에 배포하기

``` shell
$ git add dist/
$ git commit -m'프로젝트 배포!'
$ git subtree push --prefix dist origin gh-pages
```

git subtree 라는 명령어가 지정한 dist 폴더 내부의 파일들을 gh-pages 브랜치에 올려주는 작업을 진행합니다.


---

### 참고자료



[Vue 가이드][vue] <br/>
[Vue 한국어 가이드][vue-kr]<br/>
[참고한 다른 웹][other-web] 


[vue]:    https://vuejs.org/v2/guide/
[vue-kr]: https://kr.vuejs.org/v2/guide/
[vue-lifecycle]:    https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram

[velopert]: https://velopert.com/category/dev-log/tech-log/vue-js

[other-web]: https://github.com/DivanteLtd/vue-storefront/tree/gh-pages