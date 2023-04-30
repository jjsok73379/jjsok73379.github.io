---
layout: default
title: 스크립팅
parent: 유니티/최적화 방법들
nav_order: 1
---

# 스크립팅 최적화  
{: .no_toc }

  - SendMessage 와 BroadcastMessage 함수 사용자제  
  - Find 관련 함수 사용자제  
  - 자식이 많은 오브젝트 transform 변경시 많은 비용 발생  
  - Update , LateUpdate 등 함수가 비어있으면 지워라 , 빈 Update 종류 함수는 비용발생  
  - Vector2 및 Vector3 연산을 줄여라  
  - Camera.main 의 결과를 캐싱 하거나 사용하지 않고 수동으로 카메라에 대한 참조를 관리해라  