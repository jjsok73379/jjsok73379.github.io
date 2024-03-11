---
layout: default
title: 선택자 2편, 특성 선택자와 결합자
parent: CSS
nav_order: 13
---

# 선택자의 종류  
- 기본 선택자  
- 그룹 선택자  
- 특성 선택자  
- 결합 선택자  
- 의사 클래스  
- 의사 요소  

=> 이번 '선택자 2편'에서는 특성 선택자, 결합 선택자에 대해 알아보겠습니다!  

<hr>  

# 특성 선택자 1. 컨셉  
특성 선택자(속성 선택자)는 주어진 속성의 존재 여부나 그 값에 따라 요소를 선택한다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/f46eca36-bc2e-4947-bcff-0cf3624024ea)  

=> 클래스 속성을 가지고 있는 요소를 선택하기(좌)  
=> 클래스가 "item"인 요소를 선택하기(우)  

# 특성 선택자 2. 값 확인  
기호를 추가하여 요소를 선택하는 방식을 다양화할 수 있다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/0bb5399c-2c49-4613-8185-61445e110d46)  

=> 클래스 값에 "it"가 포함되는 요소를 선택하기(상)  
=> 클래스 값이 "it"로 시작하는 요소를 선택하기(중)  
=> 클래스 값이 "it"로 끝나는 요소를 선택하기(하)  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            [class$="xt"]{
                color: blue;
            }
            [id^="que"]{
                color: red;
            }
        </style>
    </head>
    <body>
        <h1>선택자 연습하기</h1>
        <p>1번 문단입니다 그냥 태그</p>
        <p class="text">2번 문단입니다 클래스 있음</p>
        <p id="unique">3번 문단입니다 아이디 있음</p>
        <p class="text">4번 문단입니다 클래스 있음</p>
        <p>5번 문단입니다 <span>스판 있는</span> 태그</p>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/239cb41c-7b8f-4515-ae7d-8219eb3c282b)  

<hr>  

# 결합 선택자 1. 컨셉  
결합 선택자(결합자)는 두 개 이상의 선택자를 결합시켜 결합된 조건을 만족하는 요소를 선택한다.  
다음 두 가지로 구분할 수 있다.  

- 자손 결합자  
- 형제 결합자  

# 결합 선택자 2. 자손 결합자  
두 개의 선택자 중 첫 번째 선택자 요소의 자손을 선택할 수 있다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/ebaa4b98-4c0c-4c4a-a164-0d102b3f09c5)  

=> div 요소 안에 위치하는 모든 p 요소를 선택하기(상)  
=> div 요소의 바로 아래에 위치하는 모든 p 요소를 선택하기(하)  

# 걸합 선택자 3. 형제 결합자  
두 개의 선택자 중 첫 번째 선택자 요소의 형제를 선택할 수 있다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/b7133fe3-4d6b-48f5-9dfe-ded52b9971ea)  

=> h1 요소의 뒤에 오는 형제 중 모든 p 요소를 선택하기(상)  
=> h1 요소의 바로 뒤에 오는 형제 p 요소를 선택하기(하)  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            body p{
                color: darkgoldenrod;
            }
        </style>
    </head>
    <body>
        <h1>선택자 연습하기</h1>
        <p>1번 문단입니다 그냥 태그</p>
        <p class="text">2번 문단입니다 클래스 있음</p>
        <p id="unique">3번 문단입니다 아이디 있음</p>
        <p class="text">4번 문단입니다 클래스 있음</p>
        <p>5번 문단입니다 <span>스판 있는</span> 태그</p>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/8f1d963b-35c2-40ca-9e4d-b9a2204687d0)  

<hr>  

````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            p > span{
                color: darkgoldenrod;
            }
        </style>
    </head>
    <body>
        <h1>선택자 연습하기</h1>
        <p>1번 문단입니다 그냥 태그</p>
        <p class="text">2번 문단입니다 클래스 있음</p>
        <p id="unique">3번 문단입니다 아이디 있음</p>
        <p class="text">4번 문단입니다 클래스 있음</p>
        <p>5번 문단입니다 <span>스판 있는</span> 태그</p>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/1ddb13ef-8b1c-4e47-ac73-79321157b834)  

<hr>  

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            p > span{
                color: darkgoldenrod;
            }
            h1 ~ p{
                color: red;
            }
        </style>
    </head>
    <body>
        <h1>선택자 연습하기</h1>
        <p>1번 문단입니다 그냥 태그</p>
        <p class="text">2번 문단입니다 클래스 있음</p>
        <p id="unique">3번 문단입니다 아이디 있음</p>
        <p class="text">4번 문단입니다 클래스 있음</p>
        <p>5번 문단입니다 <span>스판 있는</span> 태그</p>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/fdddc3ad-418a-49bc-83aa-0fc026128e36)  

<hr>  

````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            p > span{
                color: darkgoldenrod;
            }
            .text + p{
                color: red;
            }
        </style>
    </head>
    <body>
        <h1>선택자 연습하기</h1>
        <p>1번 문단입니다 그냥 태그</p>
        <p class="text">2번 문단입니다 클래스 있음</p>
        <p id="unique">3번 문단입니다 아이디 있음</p>
        <p class="text">4번 문단입니다 클래스 있음</p>
        <p>5번 문단입니다 <span>스판 있는</span> 태그</p>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/9fa219c1-3185-4132-a7c6-0352b96f6a23)