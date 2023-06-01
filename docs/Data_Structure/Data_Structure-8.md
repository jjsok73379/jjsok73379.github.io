---
layout: default
title: 트리
parent: 자료구조
nav_order: 8
---

# Tree (트리)  
{: .no_toc }

트리는 노드로 구성된 계층적 자료구조다. 최상위 노드(루트)를 만들고, 루트 노드의 child를 추가하고, 그 child에 또 child를 추가하는 방식으로 트리 구조를 구현할 수 있다.  

![image](https://velog.velcdn.com/images%2Fjha0402%2Fpost%2F74df176f-6814-4e7a-b599-275556f2338e%2Ftree_bigO.png)  

트리의 종류는 다양하다.  

트리 구조와 관련하여 반드시 알아야 할 개념들:  

  - A, B, C, D 등 트리의 구성요소를 **노드(node)** 라고 한다.  
  - 위 그림의 A처럼, 트리 구조에서 최상위에 존재하는 노드를 **root**라고 한다.  
  - 루트를 기준으로, 다른 노드로의 접근하기 위한 거리를 **depth** 라고 한다.  
  - 같은 부모를 가지면서 같은 depth에 존재하는 노드들은 **sibling** 관계에 있다.  
  - 그림에서 A는 B와 C의 **부모(parent)** 이고, B와 C는 A의 **자식(child)**이다.  
  - 노드와 노드를 잇는 선을 **edge** 라고 한다.  
  - 자식이 없는 노드는 **leaf** 라고 한다.