---
layout: default
title: inherit, initial, unset
parent: CSS
nav_order: 16
---

# 상속  
상속(Inheritance)이란 하위 요소가 상위 요소의 스타일 속성값을 물려받는 것을 의미한다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/556ee31c-8274-444a-9231-1e6862809179)  

=> li 요소를 선택하지 않았다. 그러나 상위요소 ul의 색깔이 반영되었다!  

# 다 되는 건 아니다  
상위요소로부터 상속이 이루어지는 속성이 있는 반면, 그렇지 않은 속성도 있다.  

예)  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/76f46e1c-ac25-40cb-be1e-c84cd39b9be9)  

=> 속성별 상속 여부에 대한 더 많은 정보는 아래 문서를 참고하세요!  
[https://www.w3.org/TR/CSS21/propidx.html (inherited? 항목이 상속여부)](https://www.w3.org/TR/CSS21/propidx.html)  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                display: flex;
                justify-content: center;
                align-items: center;
                width: 300px; height: 300px;

                color: tomato;
                font-size: 24px;
                border: 3px dashed red;
            }
        </style>
    </head>
    <body>
        <div>
            <p>가운데 p 태그</p>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/58c647d6-1da6-44cd-8fb4-8caf500a19a9)  

<hr>  

# 공용 키워드  
모든 CSS 속성에 사용 가능한 키워드가 있다.  
때문에 이를 '전역 값'이라 표현하기도 한다.  

<table>
    <tr>
        <th style="background-color: gray;">키워드</th>
        <th style="background-color: gray;">의미</th>
    </tr>
    <tr>
        <th>inherit</th>
        <th>상위 요소로부터 해당 속성의 값을 받아 사용한다.</th>
    </tr>
    <tr>
        <th>initial</th>
        <th>(브라우저에 지정되어 있는)해당 속성의 가본값을 요소에 적용한다.</th>
    </tr>
    <tr>
        <th>unset</th>
        <th>상속 속성에 대해서는 inherit처럼,  
        상속되지 않는 속성에 대해서는 initial처럼 적용된다.</th>
    </tr>
</table>  

**실습**  
inherit  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                display: flex;
                justify-content: center;
                align-items: center;
                width: 300px; height: 300px;

                color: tomato;
                font-size: 24px;
                border: 3px dashed red;
            }
            p{
                color: inherit;
                border: inherit;
            }
        </style>
    </head>
    <body>
        <div>
            <p>가운데 p 태그</p>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/974226aa-71d6-47ae-94b5-47d4ca79112b)  

<hr>  

initial  
**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                display: flex;
                justify-content: center;
                align-items: center;
                width: 300px; height: 300px;

                color: tomato;
                font-size: 24px;
                border: 3px dashed red;
            }
            p{
                color: initial;
                font-size: initial;
                border: initial;
            }
        </style>
    </head>
    <body>
        <div>
            <p>가운데 p 태그</p>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/8c58b772-fb01-4d06-8af4-7a41c1a6976c)  

<hr>  

unset  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                display: flex;
                justify-content: center;
                align-items: center;
                width: 300px; height: 300px;

                color: tomato;
                font-size: 24px;
                border: 3px dashed red;
            }
            p{
                color: unset;
                font-size: unset;
                border: unset;
            }
        </style>
    </head>
    <body>
        <div>
            <p>가운데 p 태그</p>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/792f3c09-f0b0-4f8b-bf56-ac89c9f61d72)