---
layout: default
title: 박스모델 1편
parent: CSS
nav_order: 4
---

# 박스모델 (Box-Model)  
브라우저가 요소를 렌더링 할 때, 각각의 요소는 기본적으로 사각형 형태의 영역을 차지하게 된다. 이 영역을 '박스'라 표현하며, CSS는 박스의 크기, 위치, 속성(색, 배경, 테두리 모양 등)을 결정할 수 있다.  
하나의 박스는 다음 네 개의 영역으로 구성된다.  
	- 콘텐츠 영역  
	- 안쪽 여백  
	- 경계선 (테두리)  
    - 바깥쪽 여백  

<hr>  

# 박스 각 영역의 크기는 어떻게?  
박스 각 영역의 크기를 정의할 수 있는 속성은 다음과 같다.  
	- 콘텐츠 영역 : width, height  
	- 안쪽 여백 : padding  
	- 바깥쪽 여백 : margin  
	- 테두리 : border-width  

<hr>  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      div{
        border: 3px solid red;
        padding: 10px;
        margin: 20px;
        width: 90px; height: 35px;
      }
      span{
        width: 100px; height: 100px;
        display: inline-block;
      }
    </style>
  </head>
  <body>
    <div>요소의 콘텐츠</div>
    <span>check</span>
  </body>
</html>
```
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/2eb78afa-ca41-438e-a70d-f296a2835e16)  
## inline-block은 인라인으로 배치하되, 블록레벨 요소의 속성을 추가하는 것!!