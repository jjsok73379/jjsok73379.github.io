---
layout: default
title: 큐
parent: 자료구조
nav_order: 3
---

# Queue(큐)  
{: .no_toc }

큐는 스택과 비슷하지만 가장 먼저 입력된 요소를 처리하는 FIFO (First In First Out) 메커니즘이다. 큐는 놀이공원에서 서는 줄과 같이 작동한다. 사람들이 맨 끝에 줄을 서고, 맨 앞에서부터 놀이기구에 탑승하는 것과 같다.  

**시간 복잡도**  

![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2F5705a000-bab6-49f3-bd03-9a6c31025f49%2Fimage.png)  
![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2Fd7e48cc1-26e9-4497-959a-0f38b5893c0b%2Fqueue.png)  

Source : Wikipedia  

**장점**  

  - 동적인 메모리 크기  
  - 데이터를 받는 순서대로 정렬된다  
  - 빠른 런타임 (runtime)  

**단점**  

  - 가장 오래된 요소만 가져온다  
  - 한번에 하나의 데이터만 처리 가능하다  

**사용**  

  - 반복적이고 자주 받는 데이터를 비동기적으로 처리할 때 효율적  
  - 음성 데이터 처럼 순서에 민감한 데이터를 처리할 때  
  - 프린트 대기열처럼 가장 먼저 입력 받은 데이터를 먼저 처리해야할 때  
  - 캐시(Cache) 구현  