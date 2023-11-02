---
layout: default
title: meta 태그
parent: HTML
nav_order: 14
---  

# meta 태그  
meta 태그는 HTML 문서에 대한 메타데이터를 정의한다.  
메타데이터란 데이터에 대한 데이터, 즉 '정보'를 의미한다.  
meta 태그는 항상 head 태그의 안에 들어가며, 일반적으로 문자 세트, 페이지 설명, 키워드, 문서의 작성자 및 뷰포트 설정을 지정하는 데 사용된다.  

<hr>  

# meta 태그를 사용하는 이유?  
웹페이지에 대한 정보를 제공 하므로 검색엔진이 페이지를 검색할 때 참고할 수 있고, 검색 결과에도 반영할 수 있다.  

<hr>  

# meta 태그가 제공하는 메타데이터의 유형 & 속성은?  
	- charset : 문자 세트  
	- http-equiv : 콘텐츠 속성 정보에 대한 http 헤더  
	- name : 문서 정보  
    - content : 메타데이터 내용  

<hr>  

# charset  
문자 인코딩에 대한 요약 정보를 기입하는 속성이다. 문자 인코딩이란 한글을 표시하기 위해 문자 세트를 지정하는 작업으로, 영문과 한글을 모두 사용하기 위해 utf-8 방식을 사용하는 것이 좋다.  
**코드 예)**  
```java
<meta charset="utf-8">
```  
=> 인코딩을 명확하게 기입해두지 않으면 웹브라우저 설정 상황에 따라 자동으로 인코딩을 추정해서 처리한다. 즉, 문자가 깨질 가능성이 생긴다.  

<hr>  

# http-equiv  
콘텐츠 속성의 정보/값에 대한 HTTP 헤더를 제공한다.
HTTP란 인터넷에서 데이터를 주고 받을 수 있는 프로토콜이다.  
**코드 예)**  
````java
<!-- IE 브라우저의 최신 버전의 엔진을 사용하라는 뜻 -->
<meta http-equiv="x-ua-compatible" content="IE=edge">
<!-- 10초마다 페이지 새로고침하라는 뜻 -->
<meta http-equiv="refresh" content="10">
````  

<hr>  

# name  
name 속성을 이름으로, content 속성을 값으로 하여 문서 정보를 이름+값 쌍의 형태로 제공할 때 사용할 수 있다.  
**코드 예)**  
```java
<!-- 문서 제작자 -->
<meta name="author" content="라돈탄">
<!-- 페이지에 대한 요약. 브라우저 즐겨찾기 페이지의 기본 설명 값 -->
<meta name="description" content="페이지에 대한 짧고 명확한 요약">
<!-- 페이지의 콘텐츠와 관련된, 쉼표로 구분한 키워드 목록 -->
<meta name="keywords" content="예를 들면, 강아지, 고양이, 정보, 반려동물, 등등">
```  

<hr>  

**실습**  
````java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="x-ua-compatible" content="IE=edge">
    <meta name="author" content="라돈탄">
    <meta name="keywords" content="메타태그, 학습, 코딩교육">
    <meta name="description" content="메타태그를 추가하는 방법">
    <title>메타태그 추가하기</title>
  </head>
  <body>
    <h1>메타태그 추가하기</h1>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/eaadef85-3b92-4984-96f2-6e633509931c)  
사진에 보이는 것처럼 웹브라우저 화면에서는 보이는 것이 없다.