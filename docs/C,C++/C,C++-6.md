---
layout: default
title: 분할구현
parent: C/C++
nav_order: 6
---

# 분할구현  
{: .no_toc }

**function.h**  
```c++
#pragma once


int Add(int a, int b);
int Sub(int a, int b);
int Mul(int a, int b);
```  

**function.cpp**  
````c++
#include "fun.h"

int Add(int a, int b) {
	return a + b;
}

int Sub(int a, int b) {
	return a - b;
}

int Mul(int a, int b) {
	return a * b;
}
````  

**main.cpp**  
```c++
#include "fun.h"

int main() {
	int data = Add(10, 20);
	data = Sub(10, 20);
	data = Mul(10, 20);

	return 0;
}
```