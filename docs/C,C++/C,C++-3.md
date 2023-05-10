---
layout: default
title: 함수
parent: C/C++
nav_order: 2
---

# Factorial 함수  
{: .no_toc }

```c++
int Factorial(int _iNum) {
	int iValue = 1;

	for (int j = 1; j < _iNum - 1; j++) {
		iValue *= (j + 2);
	}
	
	return iValue;
}

int main() {
	int iValue = Factorial(4);

	return 0;
}
```