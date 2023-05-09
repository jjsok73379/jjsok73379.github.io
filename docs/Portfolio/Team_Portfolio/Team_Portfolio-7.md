---
layout: default
title: 스텟에 따른 등급
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 7
---

# 스텟에 따른 등급  
{: .no_toc }

- 스텟에 따라서 모험가의 등급을 정해주었습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public CharState.GRADE Grade(int main)
{
    CharState.GRADE grade = new CharState.GRADE();
    if (main <= 140) // 기본스텟 40
    {
        grade = CharState.GRADE.F;
    }
    else if (main <= 640 && main > 140)
    {
        grade = CharState.GRADE.E;
    }
    else if (main <= 1640 && main > 640)
    {
        grade = CharState.GRADE.D;
    }
    else if (main <= 4640 && main > 1640)
    {
        grade = CharState.GRADE.C;
    }
    else if (main <= 9640 && main > 4640)
    {
        grade = CharState.GRADE.B;
    }
    else if (main > 9640)
    {
        grade = CharState.GRADE.A;
    }
    return grade;
}
```

</div>
</details>