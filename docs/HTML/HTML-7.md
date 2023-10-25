---
layout: default
title: 컨테이너 태그
parent: HTML
nav_order: 7
---  

# 컨테이너 태그  
콘텐츠나 레이아웃에 아무런 영향도 주지 않고, 단지 다른 요소 여럿을 묶어 관리하기 편하게 만드는 역할을 하는 태그를 '컨테이너'라고 한다.  
콘텐츠 내용을 구분하거나, 공통적인 스타일을 적용하고자 할 때 개발자는 컨테이너를 사용하는 것이 좋다.  
다음 두 가지 태그가 컨테이너 역할을 담당하는 태그들이다.  
`<div></div>` : 블록 레벨 컨테이너  
`<span></span>` : 인라인 컨테이너  

**실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>영역을 구분해보자</title>
  </head>
  <body>
    <h1>일단 문서를 만들자</h1>
    <hr>
    <div>
      <h2><span>이쁜</span> 사진</h2>
      <img src="images/study.jpg"
      width="300"
      alt="별 사진" />
      <p>별이 도는 이쁜 사진이다.</p>
    </div>
    <hr>
    <div>
      <h2><span>운동</span> 열심히 하기</h2>
      <p>pt가 너무 힘들다...</p>
    </div>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/befa0c2d-7515-47df-b6c3-e2cbfd1d75c8)