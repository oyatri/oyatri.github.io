---
layout: single
title: "[ Jekyll ] 사이드메뉴 클릭 시 해당 포스트 리스트 출력"
categories: Jekyll
---

<h2>수정 전</h2>
<br>
 사이드메뉴를 생성하였으나 사이드메뉴 클릭 시 해당 사이드메뉴에 설정한 카테고리에 대한 포스트가 아닌 모든 포스트 리스트가 출력 됐다.
<br>

<h2>진행</h2>
<br>
1: 사이드메뉴와 연결되어있는 `_pages/categories/jekyll.md` 등의 파일에서 (1) 을 주석처리한 후 (2) 를 입력 한다.

<br>
<p align="center">
    <img src="/assets/img/2022-01-11-sideMenuLink_1.png" width="50%">
</p>
<br>

(2) 에서 `site.categories.Jekyll` 은 `category`가 `Jekyll`로 설정되어있는 포스트들을 출력한다.<br>
`assign` 은 변수를 생성하는 `마크다운(markdown)` 문법이다.<br>
`Jekyll` 카테고리의 모든 포스트들을 변수 `posts`에 저장하고 (3) 을 통해 시간역순으로 출력한다.<br>


<h2>결과</h2>
<br>
해당 사이드메뉴에 설정한 카테고리를 가지고 있는 포스트들을 출력 한다.
<br>
<p align="center">
    <img src="/assets/img/2022-01-11-sideMenuLink_2.png" width="50%">
</p>
<br>

<h2>코드</h2>
<br>
`_pages/categories/jekyll.md`
~~~markdown
{% raw %}
---
layout: archive
permalink: jekyll
title: "Jekyll"
category: Jekyll

author_profile: true
sidebar:
  nav: "docs"
classes: wide
---

---

<!-- {% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %} -->

{% assign posts = site.categories.Jekyll %}

{% assign entries_layout = page.entries_layout | default: 'list' %}
<div class="entries-{{ entries_layout }}">
  {% for post in posts %}
    {% include archive-single.html type=entries_layout %}
  {% endfor %}
</div>

{% include paginator.html %}
{% endraw %}
~~~