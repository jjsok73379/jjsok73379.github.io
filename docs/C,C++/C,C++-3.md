---
layout: default
title: 함수
parent: C/C++
nav_order: 3
---

# 함수  
{: .no_toc }

- 구조가 자료구조 중 Stack과 비슷하다  

예시 : Factorial 함수  
```c++
#include <stdio.h>

int Factorial(int _iNum) {
	int iValue = 1;

	for (int j = 0; j < _iNum - 1; j++) {
		iValue *= (j + 2);
	}
	
	return iValue;
}

int main() {
	int iValue = Factorial(4);

	printf("%d", iValue);

	return 0;
}
```