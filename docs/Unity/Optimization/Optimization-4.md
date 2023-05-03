---
layout: default
title: 기타 최적화 방법
parent: 최적화 방법들
grand_parent: 유니티
nav_order: 4
---

# 기타 최적화 방법  
{: .no_toc }

프로파일링을(기본 or 툴 사용) 해서 어디서 과부화가 걸리는지 확인  

  - **에셋 관련**  
    1. 텍스처  
      - Read/Write enabled 플래그 비활성화 (기본 비활성화)  
      - 밉맵(하지만 그래픽적인 차이가 좀 있음 그러므로 상황봐서)  
      - 모든 텍스처를 압축  

    2. 모델  
      - Read/Write enabled 플래그 비활성화(기본 활성화)  
      - 애니메이션화되지 않는 모델의 리그를 비활성화  
      - 애니메이션화되는 모델에 게임 오브젝트 최적화 옵션 활성화  
      - Optimize Game Objects 활성화  
      - 가능한 한 메시 압축 사용  

  - **힙 메모리 관련**  
    1. 오브젝트 풀링 사용  
    2. 박싱을 최대한 피해야 한다.  
       ex) - enum 타입을 Dictionary 의 키로 사용하면 박싱이 발생한다.  
    3. Foreach 루프문 사용시 루프가 종료되는 시점마다 박싱이 발생했었다.(몇번 반복하든 foreach 문 하나당 한번씩)  
       버전 업그레이드를 하면서 Foreach문의 박싱은 사라졌지만 CPU 성능에 차이가 있다.(결론은 아무튼 자제 하는게 좋다.)  
    4. 배열 기반 Unity API  
       링크 : [https://docs.unity3d.com/kr/2018.2/Manual/BestPracticeUnderstandingPerformanceInUnity4-1.html](https://docs.unity3d.com/kr/2018.2/Manual/BestPracticeUnderstandingPerformanceInUnity4-1.html)  

  - **Resources 폴더사용 하지 말고 AssetBundle 을 사용하자.**  

  - **기타**  
    1. 부동 소수점보다 정수 연산의 속도가 빠르며, 부동 소수점 연산의 속도가 벡터, 매트릭스 또는 쿼터니언 연산보다 빠르다  
    2. Object.Find와 Object.FindObjectOfType의 사용을 모두 제거하는 것이 일반적으로 가장 좋다.(싱글톤은 예외)  
    3. 일차원 배열 사용, 다차원 배열이 필요한 경우 다차원 배열 말고 가변 배열을 사용  
    4. 적은 콜백 함수 사용 (Update, FixedUpdate, LateUpdate 같은)  
    5. 델리게이트 사용시 추가 제거가 자주 일어난다면 다른 데이터 구조 사용을 고려