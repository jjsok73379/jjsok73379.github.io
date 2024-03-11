---
layout: default
title: 선택자 4편, 의사요소
parent: CSS
nav_order: 15
---

# 의사요소  
의사요소(pseudo-elements)는 선택자에 추가하는 키워드로, 이를 이용하면 선택한 요소의 특정 부분에 대한 스타일을 정의할 수 있다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/3fa6b5ec-d04c-46ac-a10c-81c69144b267)  

=> li 요소의 첫 번째 글자만 크기를 20px로 하겠다(기본값은 16px)  

예시의 결과는 다음과 같다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/09d820fe-6a2e-483d-93d2-97baf8c27ed7)  

# 실습대상  

<table>
    <tr>
        <th style="background-color: gray;">의사요소</th>
        <th style="background-color: gray;">의미</th>
    </tr>
    <tr>
        <th>after</th>
        <th>요소의 앞에 의사 요소를 생성 및 추가한다.</th>
    </tr>
    <tr>
        <th>before</th>
        <th>요소의 뒤에 의사 요소를 생성 및 추가한다.</th>
    </tr>
    <tr>
        <th>first-line</th>
        <th>블록 레벨 요소의 첫 번째 선에 스타일을 적용한다.</th>
    </tr>
    <tr>
        <th>marker</th>
        <th>목록 기호의 스타일을 적용한다.</th>
    </tr>
    <tr>
        <th>placeholder</th>
        <th>입력 요소의 플레이스홀더(자리표시자) 스타일을 적용한다.</th>
    </tr>
</table>  

=> 사용 가능한 모든 의사 요소들이 궁금하다면 다음 링크를 참고하세요!  
[https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-elements)  

**실습**  
first-line, first-letter  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /*
            first-line marker placeholder before after
            */
            P::first-line{
                color: red;
            }
            p::first-letter{
                color: yellow;
            }
        </style>
    </head>
    <body>
        <p>
            퍼스트 라인 그리고 퍼스트 레터
            퍼스트 라인 그리고 퍼스트 레터
            퍼스트 라인 그리고 퍼스트 레터
            퍼스트 라인 그리고 퍼스트 레터
        </p>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/cb2b4d1d-ccd9-4621-99c6-1cbd9b33281a)  

<hr>  

marker  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /*
            first-line marker placeholder before after
            */
            P::first-line{
                color: red;
            }
            p::first-letter{
                color: yellow;
            }
            li::marker{
                color: teal;
                font-size: 60px;
            }
        </style>
    </head>
    <body>
        <ul>
            <li>강아지</li>
            <li>고양이</li>
            <li>다람쥐</li>
            <li>햄스터</li>
        </ul>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/d829b3a1-221e-4356-aad6-60811e405f1a)  

<hr>  

placeholder  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /*
            first-line marker placeholder before after
            */
            input::placeholder{
                font-size: 20px;
                color: black;
            }
        </style>
    </head>
    <body>
        <input type="text" placeholder="아무거나 쓰세요!">
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/4fd5b88a-d570-40dd-9d1e-532cf8252f47)  

<hr>  

before, after  
````html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            /*
            first-line marker placeholder before after
            */
            p::before{
                content: "앞에다 추가한 텍스트";
                color: red; font-weight: 900;
            }
            p::after{
                content: "뒤에다 추가한 텍스트";
                color: yellowgreen; font-weight: 100;
            }
        </style>
    </head>
    <body>
        <p>원래 쓰여 있던 내용</p>
    </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/7dc639f9-a1af-4b70-90d3-dceee1065584)