---
layout: default
title: input 태그
parent: HTML
nav_order: 11
---  

# input  
사용자로부터 값을 입력받을수 있는 대화형 컨트롤(또는 '필드')을 나타낸다.  
기본적으로 인라인 요소이며, 단일 태그이다.  

# input의 핵심, type 속성  
type의 값에 따라 입력 요소의 형태나 입력 데이터 유형 등이 달라진다.  
사용 가능한 type은 20여 가지이며, 기본값은 text이다.  
type의 값이 달라짐에 따라 적용할 수 있는 추가 속성의 종류도 조금씩 차이를 보인다.  

# 이름을 지어주세요  
input 태그에는 name 식별자를 추가할 수 있다.  
이는 각각의 입력 항목에 대한 이름이다. name을 통한 각 항목의 구별은 무척 중요하다.  
`<input type="text" name="nickname" />`  
`<input type="text" name="job" />`  

**실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>다양한 입력 요소 만들기</title>
  </head>
  <body>

    <input name="text" type="text" maxlength="5"
    placeholder="메시지 입력..!" /> <br> <br>

    <input name="push" type="button" value="PUSH"/> <br> <br>

    <input name="color" type="color" /> 색을 골라보세요! <br> <br>

    <input name="score" type="range" max="100" min="0"
    step="10" /> <br> <br>

    <input name="birthday" type="date" /> <br> <br>

  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/2e18b9fa-a4d9-4e8e-a965-c183e3260d16)