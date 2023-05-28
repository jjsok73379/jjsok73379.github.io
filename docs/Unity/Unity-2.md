---
layout: default
title: 코루틴
parent: 유니티
nav_order: 2
---

# 코루틴  
{: .no_toc }

## 코루틴이란?  
코루틴을 사용하면 여러 프레임에 현재 함수의 작업을 분산하여 진행할 수 있다. 함수 실행 중 yield return을 사용하여 작업을 일시 중단한 후, 다른 프레임/시간에 제어권을 다시 넘겨받아 사용하는 식이다.  

쓰레드와의 차이점은, 코루틴은 메인 스레드상에서 수행된다는 것이다.  
쓰레드의 경우 둘, 혹은 여러개의 쓰레드가 각자의 작업을 맡아 수행한다면,코루틴의 경우 한 개의 쓰레드가 ABABABAB...형식으로 각각의 작업을 조금씩 나누어 수행한다.  

![쓰레드와 코루틴의 동작 차이](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FElLv1%2FbtrvLJGOXb9%2FjiJaBA5u1J5nwHMmeCvAz0%2Fimg.png)  

**쓰레드**  

  - 별개 쓰레드에서 동작한다.  
  - 동시에 여러개의 일을 처리할 수 있다.  
  - 쓰레드는 선점형이다.  
    - 일을 하는동안에도 다른 쓰레드가 돌아가고 있다.  
    - 공유 메모리를 사용할 경우, 서로의 접근이 겹칠 수 있다.  
      - Lock을 사용할 경우, 먼저 접근한 쓰레드가 우선적으로 사용하게 된다.  
  - 비동기적이다 = 동시에 수행된다.  

**코루틴**  

  - 단일 쓰레드에서 동작한다.  
  - 여러개의 일을 나누어, 하나씩 처리한다.  
  - 코루틴은 비선점형이다.  
    - 현재 코루틴 동작이 끝날때까지, 다른 코루틴들은 대기하게 된다.  
    - 동시에 동작하지 않으므로, 메모리 접근이 겹칠 일이 없다.  
      - 현재 동작하고 있는 코루틴이 메모리를 사용하게 있을 것이다.  
  - 비동기적이 아니다 = 동시에 수행되지 않는다.  

## 코루틴과 Invoke의 차이점  

1. 코루틴은 GameObject가 활성화 일때만 동작, 인보크는 파괴 전 까지 동작  
2. 코루틴은 매개변수 전달 가능, Invoke는 불가능  
3. 코루틴은 TimeScale이 0인 경우에도 동작 시킬 수 있다.  
-> yield return new WaitForSecondsRealtime()를 사용  
4. Reflection의 차이로 코루틴의 속도가 조금 더 빠르다.  

**Reflection**  
프로그램 실행 도중에 객체의 정보 조사, 다른 모듈에 선언된 인스턴스를 생성, 기존 개체에서 형식을 가져오고 해당하는 메서드를 호출, 접근할 수 있는 강력한 기능

## 코루틴 선언  

```c#
using System.Collections; 
using UnityEngine; 

public class 클래스명 : MonoBehaviour 
{ 
    ... 
    IEnumerator 코루틴메서드명() 
    { 
        yield 반환문; 
    } 
}
```  

## 코루틴 사용  

  - StartCoroutine(routine) : 코루틴 시작. StopCoroutine 사용 후에는 사용하면, 멈춘 위치에서 다시 시작  
  - StopCoroutine(routine) : 코루틴 잠시 멈춤(중지). 다시 StartCoroutine(routine)하면, 코루틴이 계속됩니다.  
  - StopAllCoroutines() : 이 클래스내 돌고 있는 모든 코루틴 중지.  
  - SetActive(false)로 인해 연결된 게임 오브젝트가 비활성화될 때에도 코루틴이 중지됩니다.  
  - MonoBehaviour 인스턴스에서 enabled를 false로 설정하여 MonoBehaviour를 비활성화한 경우에는 코루틴이 중지되지 않습니다.  
  - 기본적으로 코루틴은 코루틴 시작 → 코루틴 중지 → 코루틴 멈춘 위치에서 다시 시작 → 코루틴 중지 ... 순으로 실행 됩니다.  
  다시 말하면, StartCoroutine → StopCoroutine 또는 StopAllCoroutines() → StartCoroutine → StopCoroutine 또는 StopAllCoroutines() ... 그래야 순차적으로 코루틴이 실행됩니다.  

````c#
using System.Collections;
using UnityEngine;

public class CoroutineExample : MonoBehaviour
{
    private IEnumerator m_Coroutine;


    void Start()
    {
        m_Coroutine = CoroutineMethod();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.A))
            StartCoroutine(m_Coroutine); // ① CoroutineMethod1 시작, ③ StopCoroutine 후 멈춘 위치에서 다시 계속
    
        if (Input.GetKeyDown(KeyCode.B))
            StopCoroutine(m_Coroutine); // ②-1 CoroutineMethod1 일시정지

        if (Input.GetKeyDown(KeyCode.C))
            StopAllCoroutines();  // ②-2 CoroutineMethod1, CoroutineMethod2 일시정지
    }

    IEnumerator CoroutineMethod()
    {
        int count = 0;

        while (true)
        {
            Debug.Log(count);
            yield return new WaitForSeconds(1.0f);
            count++;
        }
    }
}
````  

## 코루틴 재사용 (처음부터 재시작)  

StartCoroutine와 StopCoroutine이 순차적으로 반복(StartCoroutine→StopCoroutine→StartCoroutine ... )하여 코루틴을 제어하게 되면, 한번 시작한 코루틴은 계속 진행되면서 시작과 멈춤, 멈춘 위치에서 다시 시작을 반복합니다.  
그리고 코루틴 내에 정해진 실행이 완료되면 코루틴이 사실상 종료 됩니다.  
하지만, 경우에 따라서 코루틴을 처음부터 다시 사용해야 하는 경우가 있습니다.  

- **무한반복문(while문)을 종료하여, 코루틴 종료**  
코루틴을 사용 할 때, 실행 도중에 단순 반복 작업을 하기 위해 생각보다 많이 while문을 사용합니다.  
경우에 따라서, 메서드내에 무한반복문(while(true))을 사용하여 동일한 실행을 반복하고 있습니다.  
이 경우 while문의 조건을 외부 변수로 선언하여, update문 등에서 변경하여 무한반복문을 벗어나게 할 수 있습니다.  
이렇게 되면 무한반복문을 벗어나게 되고, 결국 코루틴을 완료하여 종료할 수 있습니다.  

```c#
using System.Collections;
using UnityEngine;

public class CoroutineExample : MonoBehaviour
{
    private IEnumerator m_Coroutine;
    private bool m_IsBreak; // 무한반복문 종료를 위한 변수

    void Start()
    {
        m_Coroutine = CoroutineMethod();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.A))
            StartCoroutine(m_Coroutine); 

        if (Input.GetKeyDown(KeyCode.B))
            m_IsBreak = true; // 무한반복문 종료

    }

    IEnumerator CoroutineMethod()
    {
        int count = 0;

        while (!m_IsBreak)
        {
            Debug.Log(count);
            yield return new WaitForSeconds(1.0f);
            count++;
        }
    }
}
```  

- **코루틴 상태 확인 : 실행 중 ?, 코루틴 종료 상태 확인**  
코루틴을 매개 변수에 out, ref 등을 사용할 수 없어서 코루틴 내에 실행 중이거나, 종료를 확인할 수 있는 방법이 별로 없습니다.  
하지만, 코루틴은 비동기 방식이기 때문에 경우에 따라서는 코루틴의 실행 유무나 종료 유무를 확인해야 하는 경우가 있습니다.  
이 경우에도 위와 같이 멤버변수에 bool 변수 하나를 선언하여, 코루틴의 실행 유무나 종료 유무를 확인하면 됩니다.  

````c#
using System.Collections;
using UnityEngine;

public class CoroutineExample : MonoBehaviour
{
    private IEnumerator m_Coroutine;
    private bool m_IsCoroutineing; // 코루틴 실행 유무 확인

    void Start()
    {
        m_Coroutine = CoroutineMethod();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.A))
        {
            StartCoroutine(m_Coroutine);
        }

        if(m_IsCoroutineing)
        {
            Debug.Log("코루틴이 실행 전이거나 종료되었습니다.");
        }

    }

    IEnumerator CoroutineMethod()
    {
        m_IsCoroutineing = true;

        Debug.Log("시작");

        yield return new WaitForSeconds(1.0f);
        Debug.Log("종료");

        m_IsCoroutineing = false;
    }
}
````  

- **코루틴 처음부터 재사용**  
이미 완료된 코루틴을 재사용 해야 할 경우가 있습니다.  
코루틴에도 매개변수를 사용하여, 여러가지 형태로 재사용 할 수 있습니다.  
이런 경우, 코루틴을 재할당 하여 시작하면 됩니다.  
만약, 코루틴을 제어하기 위해 사용한 멤버변수가 있다면, 경우에 따라서 값을 리셋을 해야 할 때도 있습니다.  

```c#
using System.Collections;
using UnityEngine;

public class CoroutineExample : MonoBehaviour
{
    private IEnumerator m_Coroutine;
    private bool m_IsBreak;

    void Start()
    {
        m_Coroutine = CoroutineMethod();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.A))
            StartCoroutine(m_Coroutine); // CoroutineMethod1 시작

        if (Input.GetKeyDown(KeyCode.B))
            m_IsBreak = true; // while문 break를 사용하여 CoroutineMethod while문 완료

        if (Input.GetKeyDown(KeyCode.C))
        {
            m_IsBreak= false; // 맴버 변수 리셋
            m_Coroutine = CoroutineMethod(); // CoroutineMethod 처음부터 다시 시작
            StartCoroutine(m_Coroutine);
        }
    }

    IEnumerator CoroutineMethod()
    {
        int count = 0;

        while (true)
        {
            if (m_IsBreak)
                break;

            Debug.Log(count);
            yield return new WaitForSeconds(1.0f);
            count++;
        }
    }
}
```  

## 코루틴 반환 타입  

코루틴은 아래의 반환 타입에 따라서 실행을 일시 중지하고 Unity에 제어 권한을 반환한 후 대기합니다.  

|**코루틴 반환 타입**|**설명**|
|---|---|
|yield return null;|다음 프레임까지 대기|
|yield return new WaitForSeconds(loat time);|time초만큼 대기|
|yield return new WaitForSecondsRealtime(float time);|time(Realtime)초만큼 대기|
|yield return new WaitForFixedUpdate();|다음 FixedUpdate까지 대기|
|yield return new WaitForEndOfFrame();|모든 렌더링 작업이 끝날 때까지 대기|
|yield return new WaitUntil(Func<bool> predicate);|조건을 만족할 때까지 대기|
|yield return new WaitWhile(Func<bool> predicate);|조건을 만족하지 않을 때까지 대기|
|yield return StartCoroutine(string name);|다른 코루틴이 끝날 때까지 대기|  

## 코루틴 최적화  

코루틴 내에서는 반복문(while문, for문 등)을 사용하여, 동일 실행이나 유사한 실행을 반복하는 경우가 있습니다.  
이때  변환 타입을 보면, new 연산자를 사용하여 계속 인스턴스를 생성하기 때문에 결국은 가비지를 생성하게 됩니다.  
이 것을 해결 하기 위해서 아래의 방법으로 캐싱을 하여 사용합니다.  

````c#
using System.Collections;
using UnityEngine;

public class CoroutineExample : MonoBehaviour
{
    private IEnumerator m_Coroutine;
    public static readonly WaitForSeconds m_waitForSecond2s = new WaitForSeconds(2f); // 캐싱

    void Start()
    {
        m_Coroutine = CoroutineMethod();
        StartCoroutine(m_Coroutine);
    }

    IEnumerator CoroutineMethod()
    {
        int count = 0;

        while (true)
        {
            Debug.Log(count);
            yield return m_waitForSecond2s; // 사용
            count++;
        }
    }
}
````  

## 주의 사항  

1. 코루틴이 돌아가고 있던 객체가 파괴될 시에는 코루틴이 자동으로 중단되지만, 스크립트가 Disable될 때에는 중단되지 않는다.  
  - 스크립트가 중단될 일이 있을 경우 별도의 종료 호출이 필요하다.  
2. 오브젝트가 활성화 되어있지 않은 상태에서 코루틴이 활성화될 경우 에러가 발생할 수 있다.  
  - 오브젝트를 생성(Instantiate)된 직후에 별도의 함수로 코루틴을 호출할 경우, 에러가 발생할 수 있다.  
  - 프리팹으로 생성한 오브젝트에서 코루틴을 호출할 일이 있다면, Start()에서 코루틴을 호출하게 만들어 확실히 생성된 후 코루틴을 생성하게 만드는 것이 좋을것이다.  

## 코루틴 사용의 장점  

1. Update 루프를 최적화 할 수 있다.  
2. 코드 정리를 수행할 수 있다.  

## 코루틴 사용의 단점  

가비지가 많이 생성된다.  
  - StartCoroutine을 사용할 때, 엔진 내부적으로 가비지가 다량 생성된다고 한다. -> 확인 필요  
  - 위의 소스 코드를 확인하면, yield return new ~ 의 형식으로 대기가 진행됨을 알 수 있다. yield return이 진행될때마다 새로운 인스턴스이 생성되기 때문에, 가비지 생성 문제가 생기게된다.  
    - 해당 문제를 해결하기 위해, Wait 인스턴스를 미리 만들어둔 뒤 캐싱하여 사용할 수 있다.