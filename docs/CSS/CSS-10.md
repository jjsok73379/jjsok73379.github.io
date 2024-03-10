---
layout: default
title: position 2편, fixed sticky
parent: CSS
nav_order: 10
---

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

# position: fixed;  
요소를 일반적인 문서 흐름에서 제거하고, 지정된 위치에 고정시킨다.  

```css
.pos{
    width: 200px; height: 200px;
    background: peru;
    position: fixed;
    top: 50px; left: 50px;
}
```  
=> 위에서부터 50px, 왼쪽에서부터 50px 떨어진 자리에서 움직이지 않는다!  

**실습**  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .pos{
                width: 200px; height: 200px;
                background: tomato;
                position: fixed;
                top: 200px; right: 100px;
            }
        </style>
    </head>
    <body>
        <div>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
        </div>
        <div class="pos"></div>
        <div>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/f3525521-0005-4d33-9c96-9612a6cc4bf9)  
![image](https://github.com/jjsok73379/Java/assets/114732330/6e48314d-bb7d-4f78-8ee8-c60703b37061)  

<hr>  

# position: sticky;  
요소를 일반적인 문서 흐름에 따라 배치하고, 스크롤(scroll)되는 가장 가까운 상위 요소에 대해 오프셋을 적용한다.  

```css
.pos{
    width: 200px; height: 200px;
    background: peru;
    position: sticky;
    bottom: 0px;
}
```  
=> 스크롤 이동으로 요소가 움직여도 스티키 요소는 고정된 상태를 유지한다!  

**실습**  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .pos{
                width: 200px; height: 200px;
                background: tomato;
                position: sticky;
                bottom: 0px;
            }
        </style>
    </head>
    <body>
        <div>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
            첫번째<br/>첫번째<br/>첫번째<br/>첫번째<br/>
        </div>
        <div class="pos"></div>
        <div>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
            두번째<br/>두번째<br/>두번째<br/>두번째<br/>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/0326eff5-973d-4783-9b2c-a64a8a317cab)  
![image](https://github.com/jjsok73379/Java/assets/114732330/0f9b3bc4-25e0-4502-959e-193cf1e409d8)