---
layout: default
title: 재귀 함수
parent: C/C++
nav_order: 4
---

# 재귀 함수  
{: .no_toc }

- 장점 : 가독성, 구현 용이  
- 단점 : 속도가 느리다  

예시 : Factorial 재귀 함수  
```c++
#include <stdio.h>

int Factorial_Re(int _iNum) {
	if (_iNum == 1) {
		return 1;
	}

	return _iNum * Factorial_Re(_iNum - 1);
}

int main() {
	int iValue = Factorial_Re(4);

	printf("%d", iValue);

	return 0;
}
```  

예시 : 피보나치 수열 재귀 함수  
````c++
int Fibonacci_Re(int _iNum) {
	if (_iNum == 1 || _iNum == 2) {
		return 1;
	}

	return Fibonacci_Re(_iNum - 1) + Fibonacci_Re(_iNum - 2);
}
// 엄청 오래 걸린다는 문제가 있음, 호출이 될 때마다 2의 제곱으로 늘어나서 엄청 오래 걸린다.
// 함부로 쓰면 안됨, 충분히 고려하고 적절한 곳에서만 사용해야함.

int main() {
	int iValue = Fibonacci_Re(4);

	printf("%d", iValue);

	return 0;
}
````