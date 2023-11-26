---
layout: default
title: 박스모델 4편
parent: CSS
nav_order: 7
---

# background  
배경(background)은 콘텐츠의 배경을 정의한다.  
단축 속성으로써 색상, 이미지, 반복 등 다양한 하위 속성을 정의할 수 있다.  
<table border="1">
<tr>
    <th>하위 속성</th>
    <th>역할</th>
</tr>
<tr>
    <th>background-color</th>
    <th>배경 색을 정의한다.</th>
</tr>
<tr>
    <th>background-image</th>
    <th>배경 이미지를 정의한다.</th>
</tr>
<tr>
    <th>background-position</th>
    <th>배경 이미지의 초기 위치를 정의한다.</th>
</tr>
<tr>
    <th>background-size</th>
    <th>배경 이미지의 크기를 정의한다.</th>
</tr>
<tr>
    <th>background-repeat</th>
    <th>배경 이미지의 반복 방법을 정의한다.</th>
</tr>
</table>

background-size: cover; = 이미지가 찌그러지지 않는 한도내에서 이미지가 최대사이즈가 됩니다.  
background-size: contain; = 이미지가 찌그러지거나 잘리지 않는 한도내에서 이미지가 최대사이즈가 됩니다.  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      div{
        box-sizing: border-box;
        width: 500px; height: 500px;
        border: 1px solid red;
        background-image: url(./cute_dog.jpg);
        background-repeat: no-repeat;
        background-position: center;
        background-size: contain;
      }
    </style>
  </head>
  <body>
    <div>헬로우</div>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/178634c2-11b9-4784-9f76-12d123025795)