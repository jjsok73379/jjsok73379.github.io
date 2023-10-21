---
layout: default
title: HTML 텍스트의 특징
parent: HTML
nav_order: 4
---  

# HTML 텍스트의 특징  
일반적으로 엔터는 '줄바꿈'을 의미하는 입력이지만, HTML 코드에서는 이를 무시한다. 또한 스페이스를 통한 공백도 한 번씩 밖에 인정되지 않는다.  

<hr>  

# 줄바꿈 태그와 공백문자  
HTML에서는 br 태그가 '줄바꿈'을 담당한다.  
공백을 두 번 이상 표시하고자 할 때는 &nbsp; 를 사용한다.  

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
    <p>따라서 하나의 p 태그는 자기만의 영역을 가집니다.
       <br><br><br>
      아무말 아무말 아물말....
      아무말이나 하는중....... 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      pt 너무 힘들다....
      
    </p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/0a0a3a54-51e7-4cf5-94dc-47272335d7fd)