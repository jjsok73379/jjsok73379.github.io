---
layout: default
title: 텍스트 표시 방법과 특징
parent: HTML
nav_order: 3
---  

# 1. 문단(paragraph)  
P 태그는 문단 요소를 나타내는 태그로써, 가장 많이 사용되는 텍스트 태그.  
하나의 p 태그는 하나의 문단을 표현한다. 문단과 문단 사이에는 공백이 있다.  

<hr>  

# 2. 제목(headline)  
h 태그는 제목(표제) 요소를 나타내는 태그이다.  
숫자와 함께 사용되며, 숫자 1일 때 가장 크고 6일 때 가장 작다.  

<hr>  

# 3. 수평선  
hr 태그는 수평선을 표시하는 태그이다. 수평선은 주제 변경 또는 내용 구문을 위해 주로 사용된다.  

<hr>  

**실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>텍스트 태그 연습</title>
  </head>
  <body>
    <h1>텍스트 태그 연습</h1>
    <p>텍스트 표시하고 있습니다.</p>
    <hr>
    <h2>작은 제목</h2>
    <p>제목의 크기가 바뀌었습니다.</p>
    <p>p 태그는 하나의 문단을 나타냅니다.</p>
    <p>따라서 하나의 p 태그는 자기만의 영역을 가집니다.</p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/3183c43c-2f49-4d74-ab25-a44a763284b5)