---
layout: default
title: 캡슐화
parent: 객체 지향 프로그래밍의 4가지 특징
grand_parent: 객체 지향 프로그래밍
nav_order: 1
---

# 캡슐화  
{: .no_toc }
캡슐화란 객체의 속성(data fields)과 행위(메서드, methods)를 하나로 묶고, 실제 구현 내용 일부를 외부에 감추어 은닉한다.  

## 1. 접근 제한자  

|**접근 제한자**|**접근 허용 범위**|
|:---|:---|
|private|클래스 내부만|
|protected|클래스 내부와 파생 클래스만|
|public|클래스 내부와 외부|
|internal|동일한 어셈블리 내|
|internal protected|동일한 어셈블리 내 혹은 다른 오셈블리의 파생 클래스|  

- **접근 제한자를 생략하면, 클래스는 internal, 클래스의 멤버는 private으로 설정된다.**  

## 2. 정보 은닉  
  - 필드를 public 선언하지 않는다.  
  - 필드를 외부에서 접근해야 한다면, getter와 setter를 만들고 이 메서드를 public하게 둔다.  

## 3. Property  
  - C#은 getter와 setter를 편리하게 쓸 수 있도록 property를 제공한다.  
  - Property는 메서드의 특수한 변형에 불과하다. 컴파일러가 빌드할 때, 일반적으로 알고 있는 getter와 setter 메서드로 컴파일된다.  

<details>
<summary>샘플 코드 보기</summary>
<div markdown="1">

```c#
class Program
{
    static void Main(string[] args)
    {
        Person p = new Person();
        p.Name = "Tom";
        Console.WriteLine(p.Name);
    }
}

class Person
{
    private string name;
    public string Name
    {
        get
        {
            Console.WriteLine("Getter Called.");
            return name;
        }
        set
        {
            Console.WriteLine("Setter Called.");
            name = value;
        }
    }
}
```  

- 결과  
````
Setter Called.
Getted Called.
Tom
````  

- set 구문에 있는 value는 예약어로, 프로퍼티에 대입되는 값이다.  
- p.Name은 p.name에 직접 접근하는 것이 아니라, 컴파일하며 생성되었을 get_Name이나 set_Name에 접근하는 것이다.

</div>
</details>