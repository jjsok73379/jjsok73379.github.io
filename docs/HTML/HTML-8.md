---
layout: default
title: 전역 속성
parent: HTML
nav_order: 8
---  

# 전역 속성(Global attributes)  
전역 속성은 모든 HTML 태그에서 공통으로 사용할 수 있는 속성이다. 속성이란 태그의 부가적인 기능을 정의하는 것으로, 선택사항이다.  
속성은 시작 태그의 내부에 정의한다. 속성의 개수에는 특별한 제한이 없다.  

속성을 추가하는 방법)
<태그명 속성명="속성값" 속성명="속성값">콘텐츠</태그명>  

<hr>  

# 대표적인 전역 속성들  
- id : 요소에 고유한 이름을 부여하는 식별자 역할 속성. 하나의 태그가 각기 다른 id를 가져야 한다.  
- class : 요소를 그룹 별로 묶을 수 있는 식별자 역할 속성. 여러 개의 태그가 같은 class를 가질 수 있다.  
id와 class는 사용자 정의 값을 사용한다.
- style : 요소에 적용할 CSS 스타일을 선언하는 속성.  
- title : 요소의 추가 정보를 제공하는 텍스트 속성. 사용자에게 툴팁 제공.  

더 많은 전역 속성에 대한 정보를 알고 싶다면 다음 링크를 참고하세요 : 
[https://developer.mozilla.org/ko/docs/Web/HTML/Global_attributes](https://developer.mozilla.org/ko/docs/Web/HTML/Global_attributes)  

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
    <div id="picture">
      <h2 class="title"><span>이쁜</span> 사진</h2>
      <img src="images/study.jpg"
      width="300"
      alt="별 사진" />
      <p>별이 도는 이쁜 사진이다.</p>
    </div>
    <hr>
    <div id="workout">
      <h2 class="title"><span>운동</span> 열심히 하기</h2>
      <p>pt가 너무 힘들다...</p>
    </div>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/53eef8e3-3584-4751-b617-47cac106cf48)