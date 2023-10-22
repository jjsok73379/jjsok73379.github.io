---
layout: default
title: 이미지 태그를 사용하는 방법
parent: HTML
nav_order: 6
---  

# 이미지를 보여주는 img 태그  
img 태그는 이미지를 표시할 때 사용하는 태그이다.  
단일 태그로써, 닫는 태그를 필요로 하지 않는다.  
콘텐츠를 적어주는 대신 표시할 이미지에 대한 정보를 속성으로 지정해주어야 한다.  

**기본 형태**  
`<img src="표시할이미지파일" alt="이미지설명" />`  

<hr>  

# 표시할 이미지 지정  
img 태그의 src 속성은 표시할 이미지의 위치정보와 파일명을 입력받는 속성이다. 즉, 이미지의 url을 입력받는다.  
서버에 위치한 이미지 파일이어도 되고, 내 컴퓨터에 저장된 이미지 파일이어도 된다.  
=> url이란 이미지가 어디에 있는지 알려주기 위해 사용하는 규약(형식)이다!  

<hr>  

# 이미지 설명(alt)의 중요성  
alt는 alternative의 약자로 대체 텍스트 역할을 한다.  
이미지가 로딩되기 전이나 이미지 로딩에 실패한 경우 이미지 대신에 대체 텍스트가 표시된다.  
alt를 사용하면 이미지를 볼 수 없는 시각장애인에게 웹페이지를 서비스해야 하는 상황에 대한 대비가 가능하다(음성인식기가 이미지 대신 이를 활용).  

<hr>  

# 이미지 크기 조절하기  
Img 태그를 통해 이미지를 표시할 때는 이미지가 표시될 크기를 지정할 수 있다.  
이때 너비와 높이를 각각 지정할 수 있다. 단위 없이 정수 값만 지정한다.  

`<img src="표시할이미지파일" alt="이미지설명" width="너비값" height="높이값" />`  
=> 이때 너비와 높이는 각각 픽셀(px) 단위로 적용된다. 입력 값을 넣어주지 않으면 원본 파일의 크기로 된다.  

<hr>  

**내 컴퓨터에 저장된 이미지 파일 업로드 실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>이미지를 표시해보자</title>
  </head>
  <body>
    <h1>이미지를 표시해볼게요!</h1>
    <img src="images/study.jpg" 
    alt="정말 이쁜 사진"
    width="300"/>
    <p>이미지 표시에는 img 태그</p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/c6369f32-9c2d-4e5e-8d31-0f2c68852ba8)  

<hr>  

**서버에 위치한 이미지 가져오는 실습**  
````java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>이미지를 표시해보자</title>
  </head>
  <body>
    <h1>이미지를 표시해볼게요!</h1>
    <img src="https://sitem.ssgcdn.com/87/70/47/item/1000026477087_i1_750.jpg" 
    alt="짱구 사진"
    width="300"/>
    <p>이미지 표시에는 img 태그</p>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/83e2f675-af5e-41d6-9357-2d22f24a2a59)