---
layout: default
title: float 그리고 clear
parent: CSS
nav_order: 8
---

# float  
float 속성은 요소가 문서의 일반적인 흐름에서 제외되어 자신을 포함하고 있는 컨테이너의 왼쪽이나 오른쪽에 배치되게 한다.  

<table>
    <tr>
        <th style="background-color: gray">속성값</th>
        <th style="background-color: gray">의미</th>
    </tr>
    <tr>
        <th>none</th>
        <th>기본값, 원래 상태</th>
    </tr>
    <tr>
        <th>left</th>
        <th>자신을 포함하고 있는 박스의 왼편에 떠 있어야 함</th>
    </tr>
    <tr>
        <th>right</th>
        <th>자신을 포함하고 있는 박스의 오른편에 떠 있어야 함</th>
    </tr>
</table>  

=> 문서의 흐름에선 제외되지만, 필요한 만큼의 공간은 차지한다!  

<hr>  

# clear  
clear 속성은 float 요소 이후에 표시되는 요소가 float을 해제(clear)하여 float 요소의 아래로 내려가게 할 수 있다.  

<table>
    <tr>
        <th style="background-color: gray">속성값</th>
        <th style="background-color: gray">의미</th>
    </tr>
    <tr>
        <th>none</th>
        <th>기본값, 아래로 이동되지 않음을 나타내는 키워드</th>
    </tr>
    <tr>
        <th>left</th>
        <th>float이 left인 요소의 아래로 내려가겠다</th>
    </tr>
    <tr>
        <th>right</th>
        <th>float이 right인 요소의 아래로 내려가겠다</th>
    </tr>
    <tr>
        <th>both</th>
        <th>float이 left 및 right인 요소의 아래로 내려가겠다</th>
    </tr>
</table>  
=> clear:both; 를 사용하면 한방에 해결~!  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>  
        #a{width: 100px;height: 50px;
            background-color: orange;
        float: right;}
        #b{width: 100px;height: 100px;
            background-color: royalblue;
        float: left;}
        p{
            clear: both;
        }
        </style>
    </head>
    <body>
        <div id="a"></div>
        <div id="b"></div>
        <p>안녕하세요 저는 세 번째 태그에요</p>
        <p>안녕하세요 저는 세 번째 태그에요</p>
        <p>안녕하세요 저는 세 번째 태그에요</p>
        <p>안녕하세요 저는 세 번째 태그에요</p>
        <p>안녕하세요 저는 세 번째 태그에요</p>
        <p>안녕하세요 저는 세 번째 태그에요</p>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/Java/assets/114732330/d0edbed7-b26c-4fbb-b233-1ee3981ab2bb)