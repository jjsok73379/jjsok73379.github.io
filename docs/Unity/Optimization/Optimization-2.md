---
layout: default
title: 가비지 컬렉터
parent: 최적화 방법들
grand_parent: 유니티
nav_order: 2
---

# 가비지 컬렉터(힙 메모리)  
{: .no_toc }

  - 캐싱 사용  
    우리 코드가 힙 할당으로 이어지는 함수를 반복적으로 호출하고 결과를 폐기하면 불필요한 쓰레기가 생성됩니다.  
    대신, 우리는 이러한 객체에 대한 참조를 저장하고 재사용하는 기술을 캐싱이라고 합니다.  
  - 자주 호출되는 함수에는 힙메모리 할당을 하지 않는다.  
  - 오브젝트 풀링 사용  
  - 문자열 관련  
    1. 필요한 문자열 생성을 줄여야합니다. 동일한 문자열 값을 두 번 이상 사용하는 경우 문자열을 한 번 만들고 값을 캐시해야합니다.  
    2. 우리는 불필요한 문자열 조작을 줄여야합니다. 예를 들어 자주 업데이트되고 연결된 문자열이 포함 된 텍스트 구성 요소가있는 경우 두 개의 텍스트 구성 요소로 구분할 수 있습니다.  
    3. 런타임에 문자열을 작성해야 한다면 StringBuilder 클래스를 사용해야 합니다.  
    4. 디버깅을 위해 더 이상 필요하지 않게 되면 Debug.Log ()에 대한 호출을 제거해야 합니다.  
  - 함수 관련
    1. GameObject.tag 대신 GameObject.CompareTag 사용하기  
    2. Input.GetTouch 와 Input.touchCount 대신 Input.touches 사용하기  
    3. Physics.SphereCastNonAlloc 대신 Physics.SphereCastAll 사용하기  
  - 박싱으로 이어지는 함수 호출 제거  
  - 코루틴 함수 관련  
    1. StartCoroutine 을 사용할때 약간의 가비지가 발생한다.  
    2. yield new return 에서 new 를 할때마다 가비지가 생성 된다.  
  - foreach 문 자제  
  - 수동으로 가비지컬렉터 실행 자제