---
layout: default
title: 연습문제
parent: 알고리즘
nav_order: 4
---

# 연습문제  
{: .no_toc }

**네 정수의 최댓값을 구하는 함수 max4를 작성하세요.**  
```c++
// 네 정수의 최댓값 출력
#include <stdio.h>

/*--- a, b, c, d의 최댓값 반환 ---*/
int max4(int a, int b, int c, int d)
{
    int max = a;    // 최댓값

    if (b > max) max = b;
    if (c > max) max = c;
    if (d > max) max = d;

    return max;
}

int main(void)
{
    int a, b, c, d;

    printf("네 정수의 최댓값을 구하세요.\n");
    printf("a값: ");   scanf_s("%d", &a);
    printf("b값: ");   scanf_s("%d", &b);
    printf("c값: ");   scanf_s("%d", &c);
    printf("d값: ");   scanf_s("%d", &d);

    printf("최댓값은 %d입니다.\n", max4(a, b, c, d));

    return 0;
}
```  

**세 정수의 최솟값을 구하는 min3 함수를 작성하세요.**  
````c++
// 세 정수의 최솟값 출력
#include <stdio.h>

/*--- a, b, c의 최솟값 반환 ---*/
int min3(int a, int b, int c)
{
    int min = a;    // 최솟값

    if (b < min) min = b;
    if (c < min) min = c;

    return min;
}

int main(void)
{
    int a, b, c;

    printf("세 정수의 최솟값을 구하세요.\n");
    printf("a값: ");   scanf_s("%d", &a);
    printf("b값: ");   scanf_s("%d", &b);
    printf("c값: ");   scanf_s("%d", &c);

    printf("최솟값은 %d입니다.\n", min3(a, b, c));

    return 0;
}
````  

**네 정수의 최솟값을 구하는 함수 min4를 작성하세요.**  
```c++
// 네 정수의 최솟값 출력
#include <stdio.h>

/*--- a, b, c, d의 최솟값 반환 ---*/
int min4(int a, int b, int c, int d)
{
    int min = a;    // 최솟값

    if (b < min) min = b;
    if (c < min) min = c;
    if (d < min) min = d;

    return min;
}

int main(void)
{
    int a, b, c, d;

    printf("네 정수의 최솟값을 구하세요.\n");
    printf("a값:");   scanf_s("%d", &a);
    printf("b값:");   scanf_s("%d", &b);
    printf("c값:");   scanf_s("%d", &c);
    printf("d값:");   scanf_s("%d", &d);

    printf("최솟값은 %d입니다.\n", min4(a, b, c, d));

    return 0;
}
```