---
layout: default
title: 그래프
parent: 자료구조
nav_order: 7
---

# Graph (그래프)  
{: .no_toc }

그래프는 단순히 **nodes/vertices(노드)** 사이에 **edge(엣지)**가 있는 collection이다. 그래프는 directed(방향) 또는 undirected(무방향)이 될 수 있다. Directed graph는 한쪽 방향 밖에 없어서 일방통행과 같고, undirected graph는 방향이 지정되지 않아서 양방향 도로와 같다. 하지만 그래프로 구성된 데이터 구성은 다양하다.  

그래프로 구조를 어떻게 설계 그리고 무엇을(검색, 추가, 삭제, 등) 하고 싶으냐에 따라 시간 복잡도가 달라진다.  

그래프가 리스트 형태로 설계 되어 있는 경우: N = node, E = edge  

**시간 복잡도**  

![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2F6c15078f-ace8-4441-b0e9-6ab10b808690%2Fimage.png)  
![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2Fc81001af-5047-40b3-a1a5-a44c7b8fd94b%2Fgraph2.png)  

Source: tekslate  

**장점**  

  - 새로운 요소들의 추가 / 삭제가 용이하고 효율적이다  
  - 구조의 응용이 가능하다  

**단점**  

  - 충돌이 일어날 수 있다 (입력된 키의 해시값이 이미 데이터가 저장된 버킷을 가리킬 수 있다)  

**사용**  

  - 데이터베이스 : 주소 찾기, 이름 찾기, 번호 찾기  
  - 사용자 로그인 인증