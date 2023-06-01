---
layout: default
title: 스택
parent: 자료구조
nav_order: 3
---

# Stack(스택)  
{: .no_toc }

스택은 순서가 보존되는 선형 데이터 구조 유형이다. 가장 마지막 요소 (가장 최근 요소)부터 처리하는 LIFO (Last In First Out) 메커니즘은 가지고 있다. 스택은 쌓여있는 접시 더미와 같이 작동한다. 새로운 접시가 쌓일 때도 맨 위에서 쌓이고, 접시를 가져갈 때도 맨 위에서 가지고 가는 것과 같다.  

**시간 복잡도**

![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2F5ea8515f-1fc1-4287-a4ab-7f5922df7b92%2Fimage.png)  
![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2Fda339210-5823-4b0c-9279-540c6c88d46e%2Fstack.png)  

Source : Wikipedia  

**장점**  

  - 동적인 메모리 크기  
  - 데이터를 받는 순서대로 정렬된다  
  - 빠른 런타임 (runtime)  

**단점**  

  - 가장 최신 요소만 가져온다  
  - 한번에 하나의 데이터만 처리 가능하다  

**사용**  

  - 가장 마지막으로 입력된 것을 순차적으로 바로 처리하고 싶을 때  
  - 브라우저의 뒤로가기  
  - 실행 취소  
  - 재귀  