---
layout: default
title: position 1편, relative absolute
parent: CSS
nav_order: 9
---

# position  
position은 문서 상에 요소를 배치하는 방법을 정의한다.  
position이 요소의 배치 방법을 결정하면,  
top, bottom, right, left 가 최종 위치를 결정하는 방식이다.  
```
position: 난 이렇게 배치할거야;
top: 윗면에서부터 얼만큼 떨어뜨릴거야;
right: 오른쪽면에서부터 얼만큼 떨어뜨릴거야;
bottom: 아랫면에서부터 얼만큼 떨어뜨릴거야;
left: 왼쪽면에서부터 얼만큼 떨어뜨릴거야;
```  
=> 상하좌우 위치 지정은 필요에 따라 선택적으로 사용!  

<hr>  

# position 속성값  
position 속성에는 다음 속성값들을 지정할 수 있다.  

<table>
    <tr>
        <th style="background-color: aquamarine;">속성값</th>
        <th style="background-color: aquamarine;">의미</th>
    </tr>
    <tr>
        <th style="background-color: aqua;">static</th>
        <th>기본값, 요소를 일반적인 문서 흐름에 따라 배치한다.</th>
    </tr>
    <tr>
        <th style="background-color: aquamarine;">relative</th>
        <th style="background-color: gray;">일반적인 문서 흐름에 따라 배치하되, 상하좌우 위치 값에 따라 오프셋을 적용한다.</th>
    </tr>
    <tr>
        <th style="background-color: aqua;">absolute</th>
        <th>
            일반적인 문서 흐름에서 제거하고,
            가장 가까운 position 지정 요소에 대해 상대적으로 오프셋을 적용한다.
        </th>
    </tr>
    <tr>
        <th style="background-color: aquamarine;">fixed</th>
        <th style="background-color: gray;">일반적인 문서 흐름에서 제거하고, 지정한 위치에 고정된다.</th>
    </tr>
    <tr>
        <th style="background-color: aqua;">sticky</th>
        <th>
            일반적인 문서 흐름에서 제거하고,
            스크롤 동작이 존재하는 가장 가까운 요소에 대해 오프셋을 적용한다.
        </th>
    </tr>
</table>  

<hr>  

# position: relative;  
요소를 일반적인 문서 흐름에 따라 배치하되, 상하좌우 위치 값에 따라 오프셋을 적용한다. 오프셋(보충)이란, 위치를 얼마간 이동시키는 것을 의미한다!  

```css
div{
    width: 100px; height: 100px;
    background-color: red;

    position: relative;
    top: 100px; left: 100px;
}
```  
=> 원래 위치보다 위에서부터 100px, 왼쪽에서부터 100px 떨어져 있어라!  

**실습**  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                width: 100px; height: 100px;
                background-color: red;
                position: relative;
                top: 100px; left: 50px;
            }
        </style>
    </head>
    <body>
        <div></div>
        <p>ppppppp</p>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/c8ed231b-a9ce-4b8f-b330-024bd1285446)  

<hr>  

# position: absolute;  
요소를 일반적인 문서 흐름에서 제거하고, 상위 요소 중 가장 가까운 position지정 요소에 대해 상대적으로 오프셋을 적용한다.  
position 지정 요소란, position 속성에 속성값이 정의되어 있는 요소!  
```css
div{
    width: 100px; height: 100px;
    background-color: red;

    position: absolute;
    top: 100px; left: 100px;
}
```  

**실습**  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                width: 200px; height: 200px;
                background-color: yellow;
                position: relative;
                border: 1px solid black;
            }
            .abs{
                width: 100px; height: 100px;
                background-color: red;
                position: absolute;
                top: 0px; left: 100px;
            }
        </style>
    </head>
    <body>
        <div></div>
        <div>
            <div class="abs"></div>
            <p>ppppp</p>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/4db13d24-a8e2-4226-8264-76d930660bc6)