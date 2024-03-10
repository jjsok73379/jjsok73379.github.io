---
layout: default
title: flexbox 2편, 몇 가지 관련 속성
parent: CSS
nav_order: 12
---

# 중요한 건 다시 한번  
flexbox에는 '주축(main-axis)'과 '교차축(cross-axis)'이 있다.  

![image](https://github.com/jjsok73379/Java/assets/114732330/0487155e-5346-4712-9c28-879fef43edb1)  

<hr>  

# flexbox 다루기  
flexbox를 다루기 위해 다음과 같은 속성들을 사용할 수 있다.  

- 주축 배치 방법: justift-content  
- 교차축 배치 방법: align-items  
- 교차축 개별요소 배치 방법: align-self  
- 줄 바꿈 여부: flex-wrap  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                width: 300px; height: 300px;
                border: 2px solid black;
                justify-content: space-between;
            }
            .item{
                width: 60px; height: 60px;
                background-color: teal;
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
![image](https://github.com/jjsok73379/Java/assets/114732330/ef89ad2c-ca57-4c4e-bdd5-e1c1be7f5d90)  

````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                width: 300px; height: 300px;
                border: 2px solid black;
                justify-content: space-between;
                align-items: center;
            }
            .item{
                width: 60px; height: 60px;
                background-color: teal;
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
![image](https://github.com/jjsok73379/Java/assets/114732330/ef89ad2c-ca57-4c4e-bdd5-e1c1be7f5d90)  

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
                width: 300px; height: 300px;
                border: 2px solid black;
                justify-content: space-between;
                align-items: center;
            }
            .item{
                width: 60px; height: 60px;
                background-color: teal;
            }
            .self{
                align-self: flex-start;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item self">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/Java/assets/114732330/ef89ad2c-ca57-4c4e-bdd5-e1c1be7f5d90)  

<hr>  

flex-wrap을 확인해보기 전에 flex 컨테이너의 기본적인 특성 하나 더 알아보자!  
현재 컨테이너는 300 X 300의 크기를 가지고 있는데 그 안에 있는 아이템의 크기를 컨테이너 사이즈보다 크게 한다면 어떻게 될까요?  

````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                width: 300px; height: 300px;
                border: 2px solid black;
            }
            .item{
                width: 120px; height: 60px;
                background-color: teal;
            }
            .self{
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item self">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/60fbaddd-1449-419a-8986-1d7bbcfa22d6)  


아이템이 컨테이너의 밖으로 삐져나오거나 누락되거나 할 것 같은 예상과는 달리 flex 컨테이너에서 자식 요소가 자기의 크기보다 커져버리게 되면 flex 컨테이너는 자식 요소를 줄여버립니다(수축시킨다).  
그런데 이러한 형태를 원하지 않는다면 그럴 때 사용하는 것이 `flex-wrap`입니다.  

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                width: 300px; height: 300px;
                border: 2px solid black;
                flex-wrap: wrap;
            }
            .item{
                width: 120px; height: 60px;
                background-color: teal;
            }
            .self{
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item self">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/Java/assets/114732330/d8f27b84-da22-47e2-8df0-d4e872945f72)  

````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            .container{
                display: flex;
                width: 300px; height: 300px;
                border: 2px solid black;
                flex-wrap: wrap-reverse;
            }
            .item{
                width: 120px; height: 60px;
                background-color: teal;
            }
            .self{
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="item">1</div>
            <div class="item self">2</div>
            <div class="item">3</div>
        </div>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/Java/assets/114732330/487e14ac-cfd1-42b5-90ec-c2db1eee18d2)