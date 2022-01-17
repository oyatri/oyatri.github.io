---
layout: single
title:  "[ Websquare ] DataCollection"

category: Websquare
---


<h2>정의</h2>
- 브라우저의 메모리에 할당되는 데이터를 담는 객체.<br>
- 서버에 전달하거나 서버로부터 받을 데이터 규격 정의.

<h2>종류</h2>

|<center>모델<center>|<center>설명<center>|
|---|---|
|DataMap|단 건 처리 데이터 객체|
|DataList|다 건 처리 데이터 객체|
|LinkedDataList|DataList 객체에 Filter와 Sort를 적용|

<h2>특징</h2>
- xml 구조외 XPath에 대한 이해 없이 데이터구조를 이해할 수 있는 직관적인 인터페이스 제공.
- 각 `DataCollection` 고유의 id 값을 설정할 수 있으며 이를 통해 값의 정의 및 참조 가능.
- JSON, XML, JSON Array 데이터 형식으로 SET, GET 가능.
- 초기값 설정 가능.
- 동적 생성 가능.
- 데이터 추가, 수정, 삭제 가능.
- HTML 문서의 `<head></head>` 태그 안에 작성.
<br>
<span style="font-size:10pt">※ XPath(Xml Path Language) : XML 문서의 특정 요소나 속성에 접근하기 위한 경로를 지정하는 언어 </span>

<h2>DataMap</h2>

```html
<head>
<xf:model>
  <w2:dataCollection baseNode="map">
    <w2:dataMap id="dataMap1" baseNode="userInfo">
      <w2:keyInfo>
        <w2:key id="name" name="이름" dataType="text"/>
        <w2:key id="addr" name="주소" dataType="text"/>
        <w2:key id="email" name="이메일" dataType="text"/>
      </w2:keyInfo>
      <w2:data use="true">
        <name>홍길동2</name>
        <addr>서울시 구로구</addr>
        <email>user2@mail.com</email>
      </w2:data>
    </w2:dataMap>
  </w2:dataCollection>
</xf:model>
</head>
```

<br>

~~~html
<w2:key></w2:key>
~~~

|<center>속성<center>|<center>설명<center>|
|-|-|
|id|고유 key|
|name|key 이름|
|dataType|데이터 타입 (number, text, date)<br>기본값 : text|

<br>

~~~html
<w2:data></w2:data>
~~~

|<center>속성<center>|<center>설명<center>|
|-|-|
|use|true : 입력된 데이터를 실제 초기값으로 사용<br>false : Websquare의 Design 탭에만 입력된 데이터 표시|

<h2>DataList</h2>

~~~html
<head>
<xf:model>
  <w2:dataCollection baseNode="map">
    <w2:dataList id="dataList1" baseNode="vector" repeatNode="map" valueAttribute="">
      <w2:columnInfo>
        <w2:column id="name" name="이름" dataType="text" />
        <w2:column id="addr" name="주소" dataType="text" />
        <w2:column id="email" name="이메일" dataType="text" />
      </w2:columnInfo>
    <w2:data use="true"  xmlns="">
    <w2:row>
      <name>홍길동</name>
      <addr>서울 구로구</addr>
      <email>user1@mail.com</email>
    </w2:row>
    <w2:row>
      <name>이태백</name>
      <addr>서울 강남구</addr>
      <email>user2@mail.com</email>
    </w2:row>
    </w2:data>
    </w2:dataList>
  </w2:dataCollection>
</xf:model>
</head>
~~~

<br>

~~~html
<w2:column></w2:column>
~~~

|<center>속성<center>|<center>설명<center>|
|-|-|
|id|고유 열 id<br>get/set 사용 불가|
|name|열 이름|
|dataType|데이터 타입 (number, text, date)<br>기본값 : text|

<br>

~~~html
<w2:data></w2:data>
~~~

|<center>속성<center>|<center>설명<center>|
|-|-|
|use|true : 입력된 데이터를 실제 초기값으로 사용<br>false : Websquare의 Design 탭에만 입력된 데이터 표시|

<br>

~~~html
<w2:row> <!-- 반복 데이터를 구분하는 노드 -->
      <name>이태백</name>
      <addr>서울 강남구</addr>
      <email>user2@mail.com</email>
</w2:row>
~~~

|<center>속성<center>|<center>설명<center>|
|-|-|
|<열id>|각각의 열에 대한 값 설정|