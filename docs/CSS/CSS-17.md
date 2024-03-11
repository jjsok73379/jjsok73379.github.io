---
layout: default
title: z-index
parent: CSS
nav_order: 17
---

# z-index  
z-index 속성은 요소의 쌓임 순서(stack order)를 정의할 수 있다.  
정수 값을 지정하여 쌓임 맥락(stacking context)에서의 레벨을 정의하는 방식으로 적용되며, 위치 지정 요소에 대해 적용할 수 있는 속성이다.  

=> 위치 지정 요소(positioned element)란, position 속성이 정의되어 있는 요소를 말한다.  

# 쌓임 맥락? 뭐가 쌓여?  
동일한 위치에 요소들이 배치되면, 요소들은 z축에서 쌓이게 된다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/918001e3-263a-4804-9217-b6865071ff44)  

# z-index 값은 정수로  
z-index의 기본값은 auto이다. auto는 새로운 쌓임 맥락이 형성되지 않은 자연스러운 상태이다.  

![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/4dbbe26a-3f94-483c-aa3c-4febd1b1e24c)  

**실습**  
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>HTML 문서</title>
        <style>
            div{
                width: 100px; height: 100px;
                position: relative;
            }
            div:nth-child(1){
                background-color: yellow;
            }
            div:nth-child(2){
                background-color: cyan; bottom: 50px;
            }
            div:nth-child(3){
                background-color: ivory; bottom: 100px;
            }
            div:nth-child(4){
                background-color: mediumslateblue; bottom: 150px;
            }
            .first{ z-index: 4; }
            .second{ z-index: 3; }
            .third{ z-index: 2; }
            .fourth{ z-index: 1; }
        </style>
    </head>
    <body>
        <div class="first">1</div>
        <div class="second">2</div>
        <div class="third">3</div>
        <div class="fourth">4</div>
    </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/863cef97-f551-4cc7-824b-280ceadacb6b)