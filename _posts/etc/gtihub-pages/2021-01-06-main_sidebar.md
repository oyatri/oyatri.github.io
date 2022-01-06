---
layout: single
title:  "[ Github pages ] Jekyll Main 화면 Sidebar에 category 출력"

category: github-pages
tags: [minimal mistakes, blog, github, jekyll]
---
<h2>진행</h2>
<br>
1 : `_data/navigation.yml` 파일에 Sidebar category 로 쓰기 위해 `"docs"` 로 명명한 코드를 작성한다.

<p align="center">
    <img src="/assets/img/addCategoryNav.png" width="33%">
</p>

<br>
2 : `index.html` 파일에서 빨간박스 안의 내용을 추가한다.<br>
`nav:` 에는 1: 에서 작성해준 `"docs"`를 입력한다.

<p align="center">
    <img src="/assets/img/addSidebarImg.png" width="20%">
</p>

<br>

<h2>결과</h2>
<br>
<p align="center">
    <img src="/assets/img/resultSidebar.png" width="80%">
</p>
<br>

<h2>코드</h2>
<br>
`index.html`
~~~
---
layout: home
author_profile: true
sidebar:
  nav: "docs"
---
~~~
<br>
`_data`>`navigation.yml`
~~~
# Sidebar
docs:
  - title: "FRAMEWORK"
    children:
      - title: "SPRING"
        url: /spring/

  - title: "DATABASE"
    children:
      - title: "MYSQL"
        url: /_categoris/database/mysql/
  
  - title: "ALGORITHM"
    url: /_categoris/algorithm/

  - title: "LANGUAGE"
    children:
      - title: "JAVA"
        url: /_categoris/language/java/

  - title: "ETC"
    children:
      - title: "Github pages"
        url: /_categoris/etc/gtihub-pages/
~~~

