---
layout: default
title: 상속
parent: 객체 지향 프로그래밍의 4가지 특징
grand_parent: 객체 지향 프로그래밍
nav_order: 2
---

# 상속이란?  
{: .no_toc }
베이스가 되는 클래스(부모)를 가져와서 그 위에 나만의 클래스를 **확장**해서 만드는 것.  

## 1. 상속의 장점  
  - 코드를 재활용 할 수 있다.  
  - 구조를 간결하게 할 수 있다.  
  - 필요에 따라 상속 받은 코드를 확장하여 사용도 가능  

## 2. 부모클래스 상속받는 방법  
  - 클래스 뒤에 `:` 콜론과 함께 파생할 부모클래스의 이름을 써주면 된다.  

## 3. Virtual과 Override  
Virtual과 Override는 C#에서 상속 관계 처리 시 사용 되는 메소드이다. 부모에서 동작하는 메소드를 자식에서 호출할 수 있게 만든 것.  

```c#
// 부모 코드
public class AIAgent : MonoBehaviour
{
    protected virtual void Awake()
    {
        // 부모에서 작동할 내용
    }
}

// 자식 코드
public class Daeri_Agent : AIAgent
{
    protected override void Awake()
    {
        base.Awake();
        // 자식에서 추가로 동작할 내용
    }
}
```  

이렇게 부모에서 `Awake()`를 통해 작동한 것 외에 자식에서 추가적으로 동작이 필요할 때 위와 같은 구조로 설정해주고, base.Awake()를 해주면 부모를 호출하며 **부모의 기능 + 자식의 기능**을 모두 수행할 수 있도록 해준다.