---
layout: default
title: 목록 표시하기
parent: HTML
nav_order: 10
---  

# 목록  
연관 있는 항목(item)들을 나열한 것을 의미한다.
HTML 목록은 '순서 없는 목록'과 '순서 있는 목록'으로 구분된다.  

순서 없는 목록(unorderedlist):  
`<ul></ul>`  
순서 있는 목록(orderedlist):  
`<ol></ol>`  

# 항목 태그는 같은 것을 쓴다  
`<li>`그는 목록에 들어가는 항목 하나 하나를 표현할 때 사용하는 태그이다.  
항목들(`<li>` 태그들)을 감싸는 태그가 무엇이냐에 따라 기호가 달라진다.  
=> `<ul>`, `<ol>`, `<li>` 블록 레벨 요소를 만드는 태그이다.  

**실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>목록 만들기</title>
  </head>
  <body>
    <h1>귀여운 동물 목록</h1>
    <ul>
      <li>강아지</li>
      <li><strong>고양이</strong></li>
      <li>두더쥐</li>
      <li>햄스터</li>
    </ul>
    <hr>
    <h1>프로그래밍 공부 순서</h1>
    <ol>
      <li><mark>HTML</mark></li>
      <li>CSS</li>
      <li>JAVASCRIPT</li>
      <li>NODEJS</li>
    </ol>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/751ea449-4084-4e5b-9842-df359a9feff6)