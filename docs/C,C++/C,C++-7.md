---
layout: default
title: 포인터
parent: C/C++
nav_order: 7
---

# 포인터  
{: .no_toc }

- 포인터 변수  
- 주소를 저장하는 변수  
- 자료형 + * 변수명  
- 해당 포인터에게 전달된 주소를 해석하는 단위  

 ```c++
int main() {
	// 포인터 변수
	// 주소를 저장하는 변수
	// 자료형 + * 변수명
	// 해당 포인터에게 전달된 주소를 해석하는 단위

	int i = 100;
	float f = 3.f;

    // 강제 형변환
	int* pInt = (int*)&f;

	// 주소로 접근
	i = *pInt;

	// 주소의 단위
	// BYTE

	return 0;
}
 ```