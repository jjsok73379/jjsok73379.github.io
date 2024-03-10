---
layout: default
title: 스코프 존재 이유
parent: 자바
nav_order: 3
---

# 스코프 존재 이유  
{: .no_toc }
```java
public static void main(String[] args) {
    int m = 10;
    int temp = 0;
    if (m > 0) {
        temp = m * 2;
        System.out.println("temp = " + temp);
    }
    System.out.println("m = " + m);
}
```  
조건이 맞으면 변수 `m`의 값을 2배 증가해서 출력하는 코드이다. 여기서 2배 증가한 값을 지정해두기 위해 임시 변수 `temp`를 사용했다. 그런데 이 코드는 좋은 코드라고 보기는 어렵다. 왜냐하면 임시 변수 `temp`는 `if`조건이 만족할 때 임시로 잠깐 사용하는 변수이다. 그런데 임시 변수 `temp` `main()` 코드 블록에 선언되어 있다. 이렇게 되면 다음과 같은 문제가 발생한다.  

- **비효율적인 메모리 사용**  
`temp`는 `if`코드 블록에서만 필요하지만, `main()`코드 블록이 종료될 때 까지 메모리에 유지된다. 따라서 불필요한 메모리가 낭비된다. 만약 `if`모드 블록 안에 `temp`를 선언했다면자바를 구현하는 곳에서 `if`코드 블록의 종료 시점에 이 변수를 메모리에서 제거해서 더 효율적으로 메모리를 사용할 수 있다.  
- **코드 복잡성 증가**  
좋은 코드는 군더더기 없는 단순한 코드이다. `temp`는 `if`코드 블록에서만 필요하고, 여기서만 사용하면 된다. 만약 `if`코드 블록 안에 `temp`를 선언했다면 `if`가 끝나고 나면 `temp`를 전혀 생각하지 않아도 된다. 머리속에서 생각할 변수를 하나 줄일 수 있다. 그런데 지금 작성한 코드는 `if`코드 블록이 끝나도 `main()`어디서나 `temp`를 여전히 접근할 수 있다. 누군가 이 코드를 유지보수 할 때 `m`은 물론이고 `temp`까지 계속 신경써야 한다. 스코프가 불필요하게 넓은 것이다. 지금은 코드가 매우 단순해서 이해하는데 어려움이 없겠지만 실무에서는 코드가 매우 복잡한 경우가 많다.