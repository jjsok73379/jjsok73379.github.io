---
layout: default
title: display & border
parent: CSS
nav_order: 3
---

# display 속성  
display 속성은 요소를 블록과 인라인 요소 중 어느 쪽으로 처리할지 정의한다.  
```css
/*
블록 레벨 요소인 div 요소를
인라인으로 처리하고 싶다면
*/
div{ display: inline; }
```  

````css
/*
인라인 요소인 a 요소를
블록 레벨로 처리하고 싶다면
*/
a{ display: block; }
````  

<hr>  

# display 속성 값  
display에는 미리 정의되어 있는 키워드를 속성값으로 지정한다.  
|**속성값**|의미|
|:---:|---:|
|inline|인라인으로 처리한다.|
|block|블록 레벨로 처리한다.|
|inline-block|인라인으로 배치하되, 블록레벨 요소의 속성을 추가할 수 있도록 처리한다.|
|none|디스플레이(표시)하지 않는다.|
=> 이 외에도 다양한 속성값이 있다.  

<hr>  

# border 속성  
border 속성을 사용하면 요소가 차지하고 있는 영역에 테두리를 그릴 수 있다.  
border 속성에는 속성값으로 테두리의 두께, 모양, 크기 등을 함께 지정할 수 있는데, 이러한 속성을 '단축속성'이라 한다.  
```css
span{ border: 2px solid green; }
```  
=> 두께가 2px인 직선 모양(solid)의 초록(green) 테두리를 만들어줘!  

<hr>  

# border 속성의 하위 속성  
border 속성에 지정하는 값들을 따로따로 지정할 수도 있다.  
각 속성은 다음과 같다.  
|**속성명**|속성값 예|
|:---:|---:|
|border-color|color 정의 방식과 동일|
|border-width|thin, medium, thick 등의 키워드 또는 px, em, rem 등의 단위|
|border-style|none(기본값), solid(직선), dotted(점선), dashed(긴 점선) 등|

<hr>  

**실습**  
````html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      div{ 
        border: 3px solid red;
        display: none;
      }
      span{
        border-width: 5px;
        border-style: dashed;
        border-color: rgb(100%, 50%, 0%);
        display: block;
      }
    </style>
  </head>
  <body>
    <div>나는야 블록 레벨</div>
    <span>나는야 인라인</span>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/f4acc955-6361-4779-96f7-cd02d0fc7b18)  
## none은 사라진게 아니고 안보이는 것!!