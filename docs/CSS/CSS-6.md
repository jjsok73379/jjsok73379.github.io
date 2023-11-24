---
layout: default
title: 박스모델 3편
parent: CSS
nav_order: 6
---

# box-sizing  
box-sizing 속성은 요소의 너비(width)와 높이(height)를 계산하는 방법을 지정한다.  
<table border="1">
<tr>
  <th>속성값</th>
  <th>의미</th>
</tr>
<tr>
  <th>content-box</th>
  <th>기본값. 너비와 높이가 콘텐츠 영역만을 포함한다.</th>
</tr>
<tr>
  <th>border-box</th>
  <th>너비와 높이가 안쪽 여백과 테두리까지 포함한다.</th>
</tr>
</table>
=> 너비와 높이가 같더라도, box-sizing 속성값에 따라 크기가 달라질 수 있다.  

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
        width: 100px; height: 100px;
        border: 5px solid tomato;
        padding: 30px;
      }
    </style>
  </head>
  <body>
    <div></div>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/9e17e89a-09cb-4ef2-b7d1-8d1ae1475889)