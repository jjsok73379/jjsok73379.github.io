---
layout: default
title: 반복
parent: 알고리즘
nav_order: 5
---

# 반복  
{: .no_toc }

## while문 반복  
어떤 조건이 성립하는 동안 처리(프로그램 명령문 또는 명령어의 집합)를 반복하여 실행하는 것을 반복(repetition) 구조라 하며 일반적으로 루프(loop)라고 부릅니다. 이 때 while문은 실행 전에 반복을 계속할지를 판단하는데, 이런 구조를 '사전 판단 반복' 구조라고 부릅니다. 제어식의 평갓값이 0이 아니면 프로그램 명령문이 반복됩니다.  

**while문 쓰는 법**  
```c++
/*--- while문 ---*/
식1;
while (식2)
{
	루프 본문
	식3;
}
```  

**예제**  
````c++
// 1 ~ n의 합을 구하여 출력
#include <stdio.h>

int main(void)
{
	int n;
	puts("1부터 n까지의 총합을 구합니다.");
	printf("n값 : ");
	scanf_s("%d", &n);
	int sum = 0;
	int i = 1;
	while (i <= n) 
	{
		sum += i;
		i++;
	}
	printf("1부터 %d까지의 총합은 %d입니다.\n", n, sum);

	return 0;
}
````  

## for문 반복  
하나의 변수를 사용하는 반복문은 while문보다 for문을 사용하는 것이 좋습니다.  

**for문 쓰는 법**  
```c++
/*--- for문 ---*/
for (식1; 식2; 식3)
루프 본문
```  

**예제**  
````c++
// 1 ~ n의 합을 구하여 출력
#include <stdio.h>

int main(void)
{
	int n;
	puts("1부터 n까지의 총합을 구합니다.");
	printf("n값 : ");
	scanf_s("%d", &n);
	int sum = 0;
	for (int i = 0; i <= n; i++)
		sum += i;
	printf("1부터 %d까지의 총합은 %d입니다.\n", n, sum);

	return 0;
}
````