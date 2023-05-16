---
layout: default
title: 포인터 문제
parent: C/C++
nav_order: 9
---

# 포인터 문제  
{: .no_toc }

- 문제 1  
```c++
#include <stdio.h>

int main() {
	short sArr[10] = { 1,2,3,4,5,6,7,8,9,10 };
	int* pI = (int*)sArr;
	int iData = *((short*)(pI + 2));

	printf("1번 문제 정답 : %d\n", iData);
	
	return 0;
}
```  
- 1번 문제 정답 : 5  
short형은 2바이트 int형은 4바이트이다. int포인터에 2를 더하면 short포인터에 4를 더한거와 같다. 다시 short포인터로 형변환해서 5가 나온다.

- 문제 2  
````c++
#include <stdio.h>

int main() {
	char cArr[2] = { 1,1 };
	short* pS = (short*)cArr;
	int iData = *pS;

	printf("2번 문제 정답 : %d\n", iData);
	
	return 0;
}
````  
- 2번 문제 정답 : 257  
메모리 구조가 8비트씩 해서 16인데 0000000100000001이진법으로 계산해서 257로 해석된다.