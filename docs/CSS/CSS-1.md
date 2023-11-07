---
layout: default
title: CSS 기본 문법 & 사용 방법
parent: CSS
nav_order: 1
---

# CSS 기본 문법  
선택자{  
	속성명: 속성값;  
}  

선택자 : 어떤 요소에 스타일을 적용 할지에 대한 정보  
{중괄호} : 선택한 요소에 적용할 스타일을 정의하는 영역  
속성명 : 어떤 스타일을 정의하고 싶은지에 대한 정보(색상, 크기 등)  
속성값 : 어떻게 정의하고 싶은지에 대한 정보  
예)  
```css
p{
    color: red;
}
```  
=> 그러면 p 태그가 빨간색으로 됩니다.  

<hr>  

# HTML에 CSS를 더하려면  
HTML문서에 CSS 문서(코드)를 적용하고자 할 때는 다음과 같은 방식들을 사용할 수 있다.  
	- 인라인 스타일 : 태그에 직접 기술하기  
	- 스타일 태그 : 스타일시트를 위한 태그를 추가하여 기술하기  
	- 문서 간의 연결 : 스타일시트 문서를 따로 작성하여 HTML 문서와 연결하기  

<hr>  

# 인라인 스타일  
태그에 style 속성을 추가하여 요소에 직접적으로 스타일을 정의하는 방식.  
따라서 선택자는 필요 없다.  
웹 콘텐츠와 스타일시트를 분리하기 위해서는 사용하지 않는 편이 좋다.  
예)  
````html
<p style="color: blue;">
    글자를 파랗게 만들어줘
</p>
````  

<hr>  

# 스타일 태그  
HTML 문서에 <style></style>태그를 추가하여 그 안에 CSS 코드를 작성할 수 있다.  
예)  
```html
<style>
    /* style 태그 안에는 CSS 코드를 작성해야 한다 */
    p{ color: red; }
</style>
```  

<hr>  

# 문서 간의 연결  
확장자가 *.css인 스타일시트 파일을 생성해 그 안에 CSS코드를 작성하고, HTML문서에 이를 연결해줄 수 있다. 이때는 <link>태그를 사용한다.  
예)  
````html
<link href="./style.css" rel="stylesheet">
````  
	- href : 연결하고자 하는 외부 소스의 url을 기술하는 속성  
	- rel : 현재 문서(HTML)와 외부 소스의 연관 관계를 기술하는 속성  
=> <link> 태그는 HTML문서의 <head></head> 내부에서 사용해야 한다.  

<hr>  

**인라인 스타일 실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
  </head>
  <body>
    <p style="color: blue;">
      HTML 문서를 준비하고, 에디터로 여신 다음, 내용을 작성하고 브라우저로 확인해주세요.
    </p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/6bdf4b25-6807-433e-8656-66458f158abc)  

<hr>  

**스타일 태그 실습**  
````html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      p{
        color: red;
        font-size: 32px;
      }
    </style>
  </head>
  <body>
    <p>
      HTML 문서를 준비하고, 에디터로 여신 다음, 내용을 작성하고 브라우저로 확인해주세요.
    </p>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/780afadb-9c5a-419c-be78-d8d470fc7365)  

<hr>  

**문서 간의 연결 실습**  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/483fd4e3-b5fc-4274-8389-f332d052307a)  
index.html  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <link href="./style.css" rel="stylesheet">
  </head>
  <body>
    <p>
      HTML 문서를 준비하고, 에디터로 여신 다음, 내용을 작성하고 브라우저로 확인해주세요.
    </p>
  </body>
</html>
```  

style.css  
````css
p{
    color: red;
}
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/c293b4e8-69f7-4b0b-aa7f-74d41d36f9a2)