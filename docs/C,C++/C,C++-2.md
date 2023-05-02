---
layout: default
title: 비트 연산자
parent: C/C++
nav_order: 2
---

# 비트 연산자  
{: .no_toc }

비트 연산자는 비트(bit) 단위로 논리 연산을 할 때 사용하는 연산자입니다.  
또한, 비트 단위로 전체 비트를 왼쪽이나 오른쪽으로 이동시킬 때도 사용합니다.  

|**비트 연산자**|**설명**|
|:---:|:---:|
|`&`|대응되는 비트가 모두 1이면 1을 반환함. (비트 AND 연산)|
|`|`|대응되는 비트 중에서 하나라도 1이면 1을 반환함. (비트 OR 연산)|
|`^`|대응되는 비트가 서로 다르면 1을 반환함. (비트 XOR 연산)|
|`~`|비트를 1이면 0으로, 0이면 1로 반전시킴. (비트 NOT 연산)|
|`<<`|지정한 수만큼 비트들을 전부 왼쪽으로 이동시킴. (left shift 연산)|
|`>>`|부호를 유지하면서 지정한 수만큼 비트를 전부 오른쪽으로 이동시킴. (right shift 연산)|  

다음 그림은 비트 AND 연산자(&)의 동작을 나타냅니다.  
이처럼 비트 AND 연산자는 대응되는 두 비트가 모두 1일 때만 1을 반환하며, 다른 경우는 모두 0을 반환합니다.  
![image](https://www.tcpschool.com/lectures/img_php_bitwise_and.png)  

다음 그림은 비트 OR 연산자(|)의 동작을 나타냅니다.  
이처럼 비트 OR 연산자는 대응되는 두 비트 중 하나라도 1이면 1을 반환하며, 두 비트가 모두 0일 때만 0을 반환합니다.  
![image](https://www.tcpschool.com/lectures/img_php_bitwise_or.png)  

다음 그림은 비트 XOR 연산자(^)의 동작을 나타냅니다.  
이처럼 비트 XOR 연산자는 대응되는 두 비트가 서로 다르면 1을 반환하고, 서로 같으면 0을 반환합니다.  
![image](https://www.tcpschool.com/lectures/img_php_bitwise_xor.png)  

다음 그림은 비트 NOT 연산자(~)의 동작을 나타냅니다.  
이처럼 비트 NOT 연산자는 해당 비트가 1이면 0을 반환하고, 0이면 1을 반환합니다.  
![image](https://www.tcpschool.com/lectures/img_php_bitwise_not.png)  

**사용 예시**  
```C++
#define HUNGRY   1
#define THIRSTY  2

int main(){
    unsigned int iStatus = 0;

    // 상태 추가
	iStatus |= HUNGRY;
	iStatus |= THIRSTY;

    // 상태 확인
	if (iStatus & THIRSTY) {
	}

    // 특정 자리 비트 제거
	iStatus &= ~THIRSTY;
}
```  
이런식으로 상태를 더하거나 빼줄 수 있다.