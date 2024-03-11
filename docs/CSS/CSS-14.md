---
layout: default
title: 선택자 3편, 의사클래스(가상클래스)
parent: CSS
nav_order: 14
---

# 의사클래스  
의사클래스(가상클래스)는 선택자에 추가하는 키워드로, 요소가 어떤 특정한 상태가 되었을 때 요소를 선택하겠다는 의미이다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/42a4d611-2195-4d49-b334-63a6f7d5b567)  

=> h1 요소에 마우스 커서가 올라오면(hover) 글자를 빨간색으로 하겠다!  

예시의 결과는 다음과 같다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/dc57df60-f800-425a-8bb6-1ff8bdbb0e1c)  

# 실습대상  

<table>
    <tr>
        <th style="background-color: gray;">의사클래스</th>
        <th style="background-color: gray;">의미</th>
    </tr>
    <tr>
        <th>hover</th>
        <th>마우스 포인터가 요소에 올라가 있다.</th>
    </tr>
    <tr>
        <th>active</th>
        <th>사용자가 요소를 활성화했다. (예를 들면, 마우스로 누르기와 같은)</th>
    </tr>
    <tr>
        <th>focus</th>
        <th>요소가 포커스를 받고 있다.</th>
    </tr>
    <tr>
        <th>disabled</th>
        <th>비활성 상태의 요소이다.</th>
    </tr>
    <tr>
        <th>nth-child()</th>
        <th>형제 사이에서의 순서에 따라 요소를 선택한다.</th>
    </tr>
</table>  

=> 사용 가능한 모든 의사 클래스가 궁금하다면 다음 링크를 참고하세요!  
[https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes)  

**실습**  
```html
hover  
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /* hover active focus disabled nth-child() */
            [type="button"]{
                width: 100px; height: 30px;
                background-color: tomato; color: white;
                border: none; border-radius: 8px;
            }
            [type="button"]:hover{
                background-color: gray;
            }
        </style>
    </head>
    <body>
        <input type="button" value="버튼">
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/c41a7587-9c24-4756-a47d-2e6f8dda9955)  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/f5d04d2d-aef0-4135-892a-f1ff4d1122a6)  

<hr>  

active  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /* hover active focus disabled nth-child() */
            [type="button"]{
                width: 100px; height: 30px;
                background-color: tomato; color: white;
                border: none; border-radius: 8px;
            }
            [type="button"]:hover{
                background-color: gray;
            }
            [type="button"]:active{
                background-color: black;
            }
        </style>
    </head>
    <body>
        <input type="button" value="버튼">
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/f9eed4fb-4bc4-43b5-a365-30020c228f5c)  

<hr>  

focus  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /* hover active focus disabled nth-child() */
            input:focus{
                background-color: red;
            }
        </style>
    </head>
    <body>
        <input type="text" placeholder="아무거나 쓰기">
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/5337378b-c21b-4699-a7d8-53f144fe98e4)  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/90032332-8ab9-4aad-8810-06e51a777c66)  

<hr>  

disabled  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /* hover active focus disabled nth-child() */
            input:focus{
                background-color: red;
            }
            input:disabled{
                height: 300px;
            }
        </style>
    </head>
    <body>
        <input type="text" placeholder="아무거나 쓰기" disabled>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/543e086c-ca4f-4b9c-9b23-72976b089edd)  

<hr>  

nth-child()  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /* hover active focus disabled nth-child() */
            body{
                display: flex;
                justify-content: space-between;
            }
            .box{
                width: 50px; height: 50px;
                background-color: blue; color: white;
            }
            .box:nth-child(2n - 1){
                background-color: red;
            }
        </style>
    </head>
    <body>
        <div class="box">1번</div>
        <div class="box">2번</div>
        <div class="box">3번</div>
        <div class="box">4번</div>
        <div class="box">5번</div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/fce576a6-0b71-4071-9508-b77cd814da17)