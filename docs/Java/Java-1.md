---
layout: default
title: 변수 타입
parent: 자바
nav_order: 1
---

# Java 변수 타입
{: .no_toc }
```java
//정수
byte b = 127; //-128 ~ 127 (1byte)
short s = 32767; //-32,768 ~ 32,767 (2byte)
int i = 2147483647; //-2,147,483,648 ~ 2,147,483,647 (약 20억) (4byte)

//-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807
long l = 922337203684775807L; //뒤에 L 붙여야함 (8byte)

//실수
float f = 10.0f; //뒤에 f 붙여야함, (4byte)
double d = 10.0; //float 보다 정밀도가 더 높다, (8byte)
        
//기타
boolean a = true; //불리언(boolean) true, false 입력 가능 (1byte)
char c = 'A'; //문자 하나 (1byte)
String e = "Hello Java"; //문자열, 문자열을 다루기 위한 특별한 타입 *앞에 대문자 주의, 메모리 사용량은 문자 길이에 따라 동적으로 달라진다.
```  
`String`은 첫 글자가 대문자로 시작하는 특별한 타입. 이 부분은 뒤에 클래스를 배워야 이해할 수 있다. 지금은 문자열을 다루는 특별한 타입이라고 이해하면 된다. `String`에 대한 자세한 내용은 별도로 다룬다.  

**리터럴**  
코드에서 개발자가 직접 적은 `100`, `10.5`, `'A'`, `"Hello Java"`와 같은 고정된 값을 프로그래밍 용어로 리터럴(literal)이라 한다.  

**리터럴 타입 지정**  
정수 리터럴은 `int`를 기본으로 사용한다. 따라서 `int`범위까지 표현할 수 있다. 숫자가 `int`범위인 약 20억을 넘어가면 L을 붙여서 정수 리터럴을 `long`으로 변경해야 한다. (대문자 L, 소문자 l 모두 가능하다 그런데 소문자 l은 숫자 1과 착각할 수 있어서 권장하지 않는다.)  
실수 리터럴은 기본이 `double`형을 사용한다. `float`형을 사용하려면 `f`를 붙여서 `float`형으로 지정해야 한다.