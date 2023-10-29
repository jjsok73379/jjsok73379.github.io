---
layout: default
title: 링크 표시하기
parent: HTML
nav_order: 9
---  

# 링크  
링크란 현재 문서에서 다른 문서로 이동할 수 있는 수단이다.  

# 링크는 anchor  
a 태그 요소는 href 속성을 통해 다른 페이지, 전화번호, 이메일 주소와 그 외 다른 url로 연결할 수 있는 링크(연결)를 만든다.  
인라인 요소이며, 콘텐츠는 주로 링크의 목적지를 나타낸다.  
	- <a href="https://www.naver.com">  
	    기사 양반, 네이버로 갑시다  
	</a>  
    <br> <!-- 인라인 요소이기 때문에 그냥 쓰면 서로 붙어 보이기 때문에 넣어줌 -->  

**링크 만들기 실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>링크 만들기</title>
  </head>
  <body>
    <a href="https://www.naver.com/">
      네이버로 갑시다!
    </a>
    <br>
    <a href="https://www.google.com/">
      구글로 갑시다!
    </a>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/2af8ab14-7c27-4594-8b04-cd3db9a7bfde)  

**이미지로 링크 이동**  
````java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>링크 만들기</title>
  </head>
  <body>
    <a href="https://www.naver.com/">
      <img src="images/study.jpg" width="300">
    </a>
    <br>
    <a href="https://www.google.com/">
      구글로 갑시다!
    </a>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/bcbf0977-6d7d-433c-89e7-f4d0fff51b62)  

# 새 탭에서 열고 싶다  
a 태그의 target 속성을 이용하면 새로운 문서를 열 때 현재 탑에서 열지, 새로운 탑에서 열지 결정할 수 있다.  
	- <a href="https://www.naver.com" target="_self">  
	    현재 탭에서 열기(기본값)  
	</a>  
	- <a href="https://www.naver.com" target="_blank">  
	    새 탭에서 열기  
    </a>  

**실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>링크 만들기</title>
  </head>
  <body>
    <a href="https://www.naver.com/" target="_self">
      네이버로 갑시다!
    </a>
    <br>
    <a href="https://www.google.com/" target="_blank">
      구글로 갑시다!
    </a>
  </body>
</html>
```  

# 연락을 해보자  
a 태그의 href에는 웹문서의 주소 뿐 아니라 전화번호나 메일 주소 등을 지정할 수도 있다. 이 때 각 유형별로 추가되는 텍스트가 있다.  
	- <a href="tel:010-1234-5678" target="_self">  
    전화 걸기  
    </a>  
	- <a href="mailto:ok7148@naver.com" target="_blank">  
    메일 쓰기  
    </a>  

**실습**  
````java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>링크 만들기</title>
  </head>
  <body>
    <a href="tel:010-1234-5678">
      010-1234-5678
    </a>
    <br>
    <a href="mailto:ok7148@naver.com">
      ok7148@naver.com
    </a>
  </body>
</html>
````