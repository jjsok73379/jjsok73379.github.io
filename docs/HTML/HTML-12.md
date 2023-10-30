---
layout: default
title: input 외 입력 요소들
parent: HTML
nav_order: 12
---  

# select  
select는 다수의 옵션(선택지)을 포함할 수 있는 선택 메뉴이다.  
메뉴 안에 포함되는 옵션은 option 태그를 사용해 표시한다.  
select에는 input과 마찬가지로 name을 지정할 수 있으며, 각각의 option에는 value 속성을 지정할 수 있다. value는 실제로 처리될 값을 나타낸다.  

multiple : option들이 펼쳐져 보이고 값을 요구하지 않는 속성  
사용 예) `<select name="pet" multiple>`  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/85557175-c8e7-4cc2-90a4-a3011945e79f)  

selected : 처음 선택되는 속성  
사용 예) `<option value="cat" selected>고양이</option>`  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/88ebbda3-252b-4548-a82a-485043c1fd74)  

<br>  

# textarea  
textarea는 여러 줄의 일반 텍스트를 입력할 수 있는 입력 요소이다.  
textarea역시 name을 추가하여 구별해줄 수 있는 입력 요소이다.  

**실습**  
```java
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>다양한 입력 요소 만들기</title>
  </head>
  <body>
    <h1>키우고 싶은 동물 고르기</h1>
    <select name="pet">
      <option value="dog">강아지</option>
      <option value="cat">고양이</option>
      <option value="hamster">햄스터</option>
      <option value="parrot">앵무새</option>
    </select>
    <br>
    <textarea name="content"
    rows="10" cols="10">기본적으로 쓰여 있는 텍스트</textarea>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/181cb67d-af33-497c-b875-716da6b76796)