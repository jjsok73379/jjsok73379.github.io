---
layout: default
title: flexbox 1편, 정의 및 사용 방법
parent: CSS
nav_order: 11
---

# flexbox  
flexbox란 박스 내 요소 간의 공간 배분과 정렬 기능을 제공하기 위한 1차원 레이아웃 모델이다.  
flexbox를 1차원 모델이라 부르는 이유는, 레이아웃을 다룰 때 한 번에 하나의 차원(행이나 열)만을 다룬다는 특성 때문이다.  
![image](https://github.com/jjsok73379/Java/assets/114732330/8d489e75-a933-42a1-a1b0-88c2eefb8895)  

<hr>  

# flexbox 만들기  
flexbox를 flex 컨테이너라고도 한다(요소들을 포함하기 때문).  
flex 컨테이너를 만들기 위해서는 컨테이너에 display:flex;를 적용해야 한다.  
![image](https://github.com/jjsok73379/Java/assets/114732330/619d3f9b-2522-4e57-9c6a-8d9c43f1b5fc)  

![image](https://github.com/jjsok73379/Java/assets/114732330/cfef40ec-27a2-49f8-b718-3d646312ab59)  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{ display: flex; }
            .item{
                width: 80px; height: 80px;
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/Java/assets/114732330/d9568570-3591-481f-b213-a5eb4779d0ce)  

<hr>  

# 먼저 알아야 할 것  
flexbox에는 '주축(main-axis)'과 '교차축(cross-axis)'이 있다.  

![image](https://github.com/jjsok73379/Java/assets/114732330/0487155e-5346-4712-9c28-879fef43edb1)  

<hr>  

# flex-direction  
flex-direction 속성은 flexbox 내 요소를 배치할 때 사용할 주축 및 방향(정방향, 역방향)을 지정한다.  

<table>
    <tr>
        <th style="background-color: aquamarine;">속성값</th>
        <th style="background-color: aquamarine;">의미</th>
    </tr>
    <tr>
        <th style="background-color: aqua;">row</th>
        <th>기본값, 주축은 행이고 방향은 콘텐츠의 방향과 동일</th>
    </tr>
    <tr>
        <th style="background-color: aqua">row-reverse</th>
        <th>주축은 행이고 방향은 콘텐츠의 방향과 반대</th>
    </tr>
    <tr>
        <th style="background-color: aqua;">column</th>
        <th>주축은 열이고 방향은 콘텐으의 방향과 동일</th>
    </tr>
    <tr>
        <th style="background-color: aqua;">column-reverse</th>
        <th>주축은 열이고 방향은 콘텐으의 방향과 반대</th>
    </tr>
    </tr>
</table>  

**실습**  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                flex-direction: row;
            }
            .item{
                width: 80px; height: 80px;
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
````  
row는 기본값이기에 기존과 동일  
![image](https://github.com/jjsok73379/Java/assets/114732330/d9568570-3591-481f-b213-a5eb4779d0ce)  

<hr>  

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                flex-direction: column;
            }
            .item{
                width: 80px; height: 80px;
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/Java/assets/114732330/03808f0b-fd0e-43dd-955e-77a67b7bdf17)  

<hr>  

````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                flex-direction: row-reverse;
            }
            .item{
                width: 80px; height: 80px;
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/ec15cee1-05f5-4e15-b8b5-eede1b0df579)  

<hr>  

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                flex-direction: column-reverse;
            }
            .item{
                width: 80px; height: 80px;
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/Java/assets/114732330/f69847e1-67af-426f-afe4-71f47072c275)