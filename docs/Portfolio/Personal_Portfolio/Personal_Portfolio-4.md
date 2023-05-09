---
layout: default
title: 상점
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 4
---

# 상점  
{: .no_toc }

- 수량이 1일 때 마이너스 버튼을 누르면 수량이 99로 되게 했습니다.  
- 수량이 99일 때 플러스버튼을 누르면 수량이 1로되게 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public void ClickPuls()
{
    if (num * selectedSlot.Price > GameManager.Inst.Goldvalue)
    {
        return;
    }
    else if (num == maxnum)
    {
        num = 1;
    }
    else
    {
        num++;
    }
}

public void ClickMinus()
{
    if (num <= 1)
    {
        if (GameManager.Inst.Goldvalue >= maxnum * selectedSlot.Price)
        {
            num = 99;
        }
        else
        {
            return;
        }
    }
    else
    {

        num--;
    }
}

public void ClickPulsTen()
{
    if (num * selectedSlot.Price > GameManager.Inst.Goldvalue)
    {
        return;
    }
    else if (num == maxnum)
    {
        num = 1;
    }
    else if (num + 10 >= maxnum)
    {
        num = maxnum;
    }
    else
    {
        num += 10;
    }
}

public void ClickMinusTen()
{
    if (num <= 1)
    {
        if (GameManager.Inst.Goldvalue >= maxnum * selectedSlot.Price)
        {
            num = 99;
        }
        else
        {
            return;
        }
    }
    else if (num - 10 <= 1)
    {
        num = 1;
    }
    else
    {

        num -= 10;
    }
}
```

</div>
</details>