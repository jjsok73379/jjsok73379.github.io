---
layout: default
title: 표현 방법
parent: 알고리즘
nav_order: 2
---

# 알고리즘의 표현 방법  
{: .no_toc }

## 1. 자연어  

사람이 사용하는 국어나 영어와 같은 언어를 이용해 나타내는 방법  

## 2. 순서도  

주어진 문제를 해결하거나 업무를 처리할 때, 처리할 일의 순서를 한 단계씩 구분하여 약속된 도형으로 표현한 그림  

![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fcijwd5%2FbtqVOrCTri7%2Fjg2bGrYj005kgrnsIa7k7K%2Fimg.png)  

## 3. 의사코드  

자연어로 표현한 것을 연상 기호 등을 사용하여 쉽고 간단하게 문제의 처리 과정을 표현한 것  

```
A <- 1 // A에 1을 저장한다.
B <- 1 // B에 1을 저장한다. 
SUM <- A+B // A와 B를 더한 것을 SUM에 저장한다.
if(A>B) 
then print A //A가 B보다 크면 A를 출력한다.
else print "감자"//아니라면 "감자"를 출력한다.
```  

## 4. 프로그래밍 언어  

Java, C언어, C++ 등을 이용하여 나타낸 것  

```C
public class Main  {
    public Main(){
        int a = 1;
        int b = 1;
        System.out.println(a);
        if(a > b){
            System.out.println(b);
        }
    }
    public static void main(String[] args) {
	// write your code here
    new Main();
    }
}
```