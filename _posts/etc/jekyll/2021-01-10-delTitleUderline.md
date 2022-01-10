---
layout: single
title: "[ Jekyll ] minimal-stakes 포스트 리스트 제목 밑줄 제거"
category: Jekyll
---

<h2>수정 전</h2>
<br>
밑줄이 왠지 거슬린다.
<br>
<p align="center">
    <img src="/assets/img/2021-01-10_delTitleUderline_1.png" width="70%">
</p>

<h2>진행</h2>
<br>
1 : `_sass/minimal-mistakes/_base.scss` 파일의 빨간 박스 부분에 해당 코드를 작성한다.
<br>
<p align="center">
    <img src="/assets/img/2021-01-10_delTitleUderline_2.png" width="35%">
</p>

<h2>결과</h2>
<br>
밑줄이 사라진 것을 확인할 수 있다.
<br>
<p align="center">
    <img src="/assets/img/2021-01-10_delTitleUderline_3.png" width="70%">
</p>

<h2>코드</h2>
<br>
~~~
/* links */

a {

  /* a link 하이퍼링크 밑줄 없애기 */
  text-decoration: none;

  &:focus {
    @extend %tab-focus;
  }

  &:visited {
    color: $link-color-visited;
  }

  &:hover {
    color: $link-color-hover;
    outline: 0;
  }
}
~~~