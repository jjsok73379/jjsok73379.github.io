---
layout: default
title: 코드
parent: 마크다운
nav_order: 4
---

# 코드  
{: .no_toc }

4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다.  

## 2.4.1 들여쓰기  

```
This is a normal paragraph:

    This is a code block.
    
end code block.
```  

실제로 적용해보면,  

적용예 :  
This is a normal paragraph:

    This is a code block.
    
end code block.  

## 2.4.2 코드블럭  

코드블럭은 다음과 같이 2가지 방식을 사용할 수 있습니다.  

  - `<pre><code>{code}</code></pre>` 이용방식  

```
<pre>
<code>
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }

}
</code>
</pre>
```

<pre>
<code>
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }

}
</code>
</pre>


  - 코드블럭코드("```") 을 이용하는 방법  

````
```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```
````  

```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```  

**깃헙**에서는 코드블록코드("```") 시작점에 사용하는 언어를 선언하여 [문법강조(Syntax highlighting)](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting)이 가능하다.  

````
```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```
````  

```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```