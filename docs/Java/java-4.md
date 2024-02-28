---
layout: default
title: 자바에서 계산
parent: 자바
nav_order: 4
---

# 자바에서 계산  
{: .no_toc }

1. **같은 타입끼리의 계산은 같은 타입의 결과를 낸다.**  
- `int` + `int`는 `int`를, `double` + `double`은 `double`의 결과가 나온다.  
2. **서로 다른 타입의 계산은 큰 범위로 자동 형변환이 일어난다.**  
- `int` + `long`은 `long` + `long`으로 자동 형변환이 일어난다.  
- `int` + `double`은 `double` + `double`로 자동 형변환이 일어난다.  

다양한 타입별로 더 자세히 들어가면 약간 차이가 있지만 이 기준으로 이해하면 충분하다.