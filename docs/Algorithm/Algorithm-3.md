---
layout: default
title: 알고리즘의 정의
parent: 알고리즘
nav_order: 3
---

# 알고리즘의 정의  
{: .no_toc }
'알고리즘이란 무엇인가?'를 간단한 프로그램을 통해 알아보겠습니다. 3개의 정숫값 가운데 최댓값을 구하는 프로그램입니다.  

```c++
// 세 정수의 최댓값을 구하는 프로그램
#include <stdio.h>

/*--- a, b, c의 최댓값을 구하여 반환 ---*/
int max3(int a, int b, int c)
{
	int max = a; // 최댓값
	if (b > max) max = b;
	if (c > max) max = c;
	return max; // 구한 최댓값을 호출한 곳으로 반환
}

int main(void)
{
	printf("max3(%d, %d, %d) = %d\n", 3, 2, 1, max3(3, 2, 1));
	printf("max3(%d, %d, %d) = %d\n", 3, 2, 2, max3(3, 2, 2));
	printf("max3(%d, %d, %d) = %d\n", 3, 1, 2, max3(3, 1, 2));
	printf("max3(%d, %d, %d) = %d\n", 3, 2, 3, max3(3, 2, 3));
	printf("max3(%d, %d, %d) = %d\n", 2, 1, 3, max3(2, 1, 3));
	printf("max3(%d, %d, %d) = %d\n", 3, 3, 2, max3(3, 3, 2));
	printf("max3(%d, %d, %d) = %d\n", 3, 3, 3, max3(3, 3, 3));
	printf("max3(%d, %d, %d) = %d\n", 2, 2, 3, max3(2, 2, 3));
	printf("max3(%d, %d, %d) = %d\n", 2, 3, 1, max3(2, 3, 1));
	printf("max3(%d, %d, %d) = %d\n", 2, 3, 2, max3(2, 3, 2));
	printf("max3(%d, %d, %d) = %d\n", 1, 3, 2, max3(1, 3, 2));
	printf("max3(%d, %d, %d) = %d\n", 2, 3, 3, max3(2, 3, 3));
	printf("max3(%d, %d, %d) = %d\n", 1, 2, 3, max3(1, 2, 3));
	return 0;
}
```  

계산 결과를 쉽게 확인하기 위해 최댓값이 3이 되도록 실인수를 조합했습니다. 프로그램을 실행하면 13가지의 조합에 대해 모두 3이 출력되어 최댓값이 바르게 구해진 것을 확인할 수 있습니다.  

이처럼 '알고리즘'은 다음과 같이 정의할 수 있습니다.  

**어떤 문제를 해결하기 위한 절차로, 명확하게 정의되고 순서가 있는 유한 개의 규칙으로 이루어진 집합**