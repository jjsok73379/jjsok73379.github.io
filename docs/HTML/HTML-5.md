---
layout: default
title: 태그의 구분 & 인라인 텍스트 요소
parent: HTML
nav_order: 5
---  

# 태그의 구분  
블록 레벨 요소를 만드는 태그 vs 인리인 요소를 만드는 태그  

인터넷에서 F12로 개발자도구를 열어서 확인이 가능하다.  

<hr>  

## 블록 레벨 요소  
자기가 속한 영역의 너비를 모두 차지하여 블록을 형성한다. (ex. h, p)  

<hr>  

## 인라인 요소  
자기에게 필요한 만큼의 공간만 차지한다. (ex. strong, em, mark)  

### 1. strong 태그  
strong 태그는 감싸고 있는 콘텐츠를 굵게 표시하는 태그이다.  
예시  
```java
<p>
    굵게 표시하고 싶은 부분은 어디? <strong>바로 여기!</strong>
</p>
```  

### 2. em 태그  
em 태그는 감싸고 있는 콘텐츠를 기울여 이탤릭체로 표시하는 태그이다.  
예시  
````java
<p>
    기울게 표시하고 싶은 부분은 어디? <em>바로 여기!</em>
</p>
````  

### 3. mark 태그  
mark 태그는 감싸고 있는 콘텐츠에 형광펜 표시를 더해주는 태그이다.  
예시  
```java
<p>
    형광펜 표시하고 싶은 부분은 어디? <mark>바로 여기!</mark>
</p>
```  

<hr>  

**실습**  
````java
<p>
    형광펜 표시하고 싶은 부분은 어디? <mark>바로 여기!</mark>
</p>

실습
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>태그의 구분과 텍스트 태그</title>
  </head>
  <body>
    <h1>제목을 표시하는 큰 텍스트!</h1>
    <p>문단을 나타내는 작은 (?) 텍스트!
      <strong>p 태그 안에서 굵게 표시하기</strong>
      <em>p 태그 안에서 기울게 표시하기</em>
      이 태그는 블록 요소를 만들까요?
      <mark>p 태그 안에서 밝게 표시하기</mark>
      아니면 인라인 요소를 만들까요!?
    </p>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/bd8c3c24-3202-48f2-ace7-3aa91e3a7d86)