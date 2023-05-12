---
layout: default
title: 배열, 구조체
parent: C/C++
nav_order: 5
---

# 배열, 구조체  
{: .no_toc }

## 배열  

```c++
int main() {
	// 배열
	// 메모리가 연속적
	// iArray[]안에 원하는 수 - 1
	// iArray[]안에 수가 배열보다 크면 다른 값 침범 가능성이 있다.
    // {}에 값을 따로 안넣어주면 0으로 된다.
	int iArray[10] = {};

	return 0;
}
```  

## 구조체  

````c++
#include <stdio.h>

// 사용자 정의 자료형
typedef struct _tagMyST
{
	int a;
	float f;
}MYST; // 구조체 이름 부여

typedef struct _tagBig
{
	MYST k;
	int i;
	char c;
}BIG;

typedef int INT; // 새로운 이름 부여

int main() {
	// 구조체
	MYST t = {100, 3.14f}; // 숫자 부여 가능
	t.a = 10;
	t.f = 10.2312f;

	int iSiae = sizeof(MYST);

	INT a;

	return 0;
}
````