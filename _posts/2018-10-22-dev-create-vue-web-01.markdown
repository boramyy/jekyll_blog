---
layout: post
title: "vue로 todo페이지 만들기"
date: 2018-10-22
permalink: /dev/javascript/vue/01
categories: development
tags: ['vue', 'javascript']
published: true
---

### vue 란?

[vue에 대해 잘 정리된 Velopert님의 글][velopert]{:target="_blank"}

### vue cli 설치하기
```
  npm install -g @vue/cli
```

### vue lifecycle diagram
[Vue Lifecycle][vue-lifecycle]{:target="_blank"}


### 폴더 구조

``` shell
  
  /dist
    └ ...
  /node_modules
  /public
    ├ favicon.ico
    └ index.html
  /src 
    └ /assets
      └ logo.png
    └ /components
      ├ Todo.vue
      ├ TodoHeader.vue
      ├ TodoBody.vue
      └ TodoFooter.vue
    └ App.vue
  .gitignore
  babel.config.js

```


---

### 참고자료

[Vue 가이드][vue]{:target="_blank"} <br/>
[Vue 한국어 가이드][vue-kr]{:target="_blank"}


[vue]:    https://vuejs.org/v2/guide/
[vue-kr]: https://kr.vuejs.org/v2/guide/
[vue-lifecycle]:    https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram

[velopert]: https://velopert.com/category/dev-log/tech-log/vue-js