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

예시 : 피보나치 수열 함수
````c++
// 피보나치 수열
// 1 1 2 3 5 8 13 21 34 55......
int Fibonacci(int _iNum) {
	if (_iNum == 1 || _iNum == 2) {
		return 1;
	}

	int iPrev1 = 1;
	int iPrev2 = 1;
	int iValue = 0;

	for (int i = 0; i < _iNum - 2; i++) {
		iValue = iPrev1 + iPrev2;
		iPrev1 = iPrev2;
		iPrev2 = iValue;
	}

	return iValue;
}

int main() {
	int iValue = Fibonacci(4);

	printf("%d", iValue);

	return 0;
}
````