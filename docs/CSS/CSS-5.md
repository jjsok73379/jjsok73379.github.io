---
layout: default
title: 박스모델 2편
parent: CSS
nav_order: 5
---

# 다양한 경우의 수  
여백은 상하좌우 네 개의 면에 존재하는 영역이다.  
작성자는 각 면에 개별적으로 두께를 정의할 수 있다.  
이를 위해 다음 두 가지 방법을 사용한다.  
	- 하위 속성 정의하기  
	- 여러 값을 한 번에 정의하기  

<hr>

# 하위 속성 정의하기  
상하좌우 여백을 정의할 수 있는 개별 속성들이 있다.  
**하위 속성 정의하기 실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      div{
        width: 100px; height: 100px;
        padding: 10px;
        border: 5px solid red;
        margin: 20px;
        padding-top: 10px;
        padding-right: 20px;
        padding-bottom: 30px;
        padding-left: 40px;
        margin-top: 40px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-left: 10px;
      }
    </style>
  </head>
  <body>
    <div></div>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/21665af1-784c-40bf-86e4-b8517488d413)  

<hr>  

# 여러 값을 한 번에 정의하기  
padding과 margin은 네 면의 여백에 대한 단축속성이다.  
````css
span{
    display: inline-block;
    width: 100px; height: 100px;
    margin: 10px 20px 30px 40px;
}
````  

**여러 값을 한 번에 정의하기 실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      div{
        width: 100px; height: 100px;
        border: 5px solid red;
        margin: 10px 30px 20px 40px;
      }
    </style>
  </head>
  <body>
    <div></div>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/0bb4ca8f-bb45-44dc-8822-e91a24ed4185)