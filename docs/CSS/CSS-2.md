---
layout: default
title: 선택자 1편
parent: CSS
nav_order: 2
---

# 선택자  
선택자{  
	속성명: 속성값;  
}  
선택자 : 어떤 요소에 스타일을 적용할 것인지에 대한 정보  

<hr>  

# 선택자의 종류  
	- 기본 선택자  
	- 그룹 선택자  
	- 특성 선택자  
	- 결합 선택자  
	- 의사 클래스  
    - 의사 요소  

<hr>  

# 기본 선택자 1. 전체 선택자  
모든 요소를 선택한다.  
*(애스터리스크)는 '문서 내의 모든 요소'를 의미하는 기호이다.  
```css
*{
    color: blue;
}
```  
=> 문서 내 모든 요소의 글자 색을 파란색으로 지정한다.  

# 기본 선택자 2. 태그 선택자  
주어진 이름을 가진 요소를 선택한다. '유형 선택자'라고도 한다.  
주어진 이름을 가진 요소가 다수일 경우, 해당 요소들을 모두 선택한다.  
````css
p{
    color: blue;
}
````  
=> 문서 내 모든 p 태그 요소의 글자 색을 파란색으로 지정한다.  

# 기본 선택자 3. 클래스 선택자  
주어진 class속성값을 가진 요소를 선택한다.  
주어진 class속성값을 가진 요소가 다수일 경우, 해당 요소를 모두 선택한다.  
text앞에 . : '나는 클래스를 고르겠다'라는 의미  
```css
.text{
    color: blue;
}
```  
=> 문서 내 class가 "text"인 모든 요소의 글자 색을 파란색으로 지정한다.  

# 기본 선택자 4. 아이디 선택자  
주어진 id속성값을 가진 요소를 선택한다.  
id는 고유한(unique) 식별자 역할을 하는 전역 속성이다.  
topic앞에 # : 'topic이라는 아이디'를 가진 요소  
````css
#topic{
    color: blue;
}
````  
=> 문서 내 id가 "topic"인 요소의 글자 색을 파란색으로 지정한다.  

<hr>  

# 그룹 선택자  
다양한 유형의 요소를 한꺼번에 선택하고자 할 때 사용한다.  
쉽표(,)를 이용해 선택자를 그룹화한다.  
```css
h1, p, div{
    color: blue;
}
```  
=> 문서 내 모든 h1, p, div 태그 요소의 글자 색을 파란색으로 지정한다.  

<hr>  

# 선택자가 겹치는 경우  
선택자가 겹치는 경우, 기본적으로 나중에 작성된 스타일이 적용된다.  
선택자가 다르지만 요소가 겹치는 경우, 선택자 우선순위에 의해 적용될 스타일이 결정된다.  
선택자 우선순위  
**아이디 선택자** > **클래스 선택자** > **태그 선택자**  

<hr>  

**전체 선택자 실습**  
````html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      *{
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>제목을 나타낸다!</h1>
    <p>문단을 표시한다 가가가</p>
    <p>문단을 표시한다 나나나</p>
    <p>문단을 표시한다 다다다</p>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/18402800-8e8d-4173-a638-5cbf4fdd4a6a)  

<hr>  

**태그 선택자 실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      h1{
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>제목을 나타낸다!</h1>
    <p>문단을 표시한다 가가가</p>
    <p>문단을 표시한다 나나나</p>
    <p>문단을 표시한다 다다다</p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/a93099f9-877e-4f82-835c-95ba3f020efd)  

<hr>  

**클래스 선택자 실습**  
````html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      .text{
        color: red;
      }
    </style>
  </head>
  <body>
    <h1 class="text">제목을 나타낸다!</h1>
    <p>문단을 표시한다 가가가</p>
    <p class="text">문단을 표시한다 나나나</p>
    <p>문단을 표시한다 다다다</p>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/b5d4eeeb-1514-4ba6-8800-4983334f8a56)  

<hr>  

**아이디 선택자 실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      .text{
        color: red;
      }
      #gagaga{
        color: blue;
      }
    </style>
  </head>
  <body>
    <h1 class="text">제목을 나타낸다!</h1>
    <p id="gagaga">문단을 표시한다 가가가</p>
    <p class="text">문단을 표시한다 나나나</p>
    <p>문단을 표시한다 다다다</p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/39773c44-4d5b-4515-9db3-52561d4e2a51)  

<hr>  

**그룹 선택자 실습**  
````html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      h1, p{
        color: purple;
      }
    </style>
  </head>
  <body>
    <h1 class="text">제목을 나타낸다!</h1>
    <p id="gagaga">문단을 표시한다 가가가</p>
    <p class="text">문단을 표시한다 나나나</p>
    <p>문단을 표시한다 다다다</p>
  </body>
</html>
````  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/59763f5a-0c85-4921-aa37-58d9454532bc)  

<hr>  

**우선순위를 알아보는 실습**  
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>HTML 문서</title>
    <style>
      .text{ color: red; }
      h1{ color: blue; }
    </style>
  </head>
  <body>
    <h1 class="text">제목을 나타낸다!</h1>
    <p id="gagaga">문단을 표시한다 가가가</p>
    <p class="text">문단을 표시한다 나나나</p>
    <p>문단을 표시한다 다다다</p>
  </body>
</html>
```  
![image](https://github.com/jjsok73379/jjsok73379.github.io/assets/114732330/8f3f8bad-e157-4a3f-8bb5-2af8c0d7770a)