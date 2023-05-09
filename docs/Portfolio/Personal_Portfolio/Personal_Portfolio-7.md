---
layout: default
title: 스킬 속성
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 7
---

# 스킬 속성(디버프)  
{: .no_toc }

- 디버프 Type을 정해주고 디버프 리스트에 추가되면 해당 행동을 하게 했습니다.  
- 얼음은 느려지게, 화염은 대미지가 더 강하게, 번개는 스턴에 걸려 행동을 멈추게 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
void Update()
{
    for (int i = 0; i < debuffList.Count;)
    {
        Debuff temp = debuffList[i];
        temp.keepTime -= Time.deltaTime;
        if (temp.keepTime <= 0.0f)
        {
            switch (temp.type)
            {
                case Debuff.Type.Slow:
                    SlowMoveSpeed /= temp.value;
                    break;
                case Debuff.Type.Stun:
                    StunMoveSpeed /= temp.value;
                    break;
            }
            debuffList.RemoveAt(i);
            continue;
        }
        debuffList[i] = temp;
        ++i;
        if (debuffList.Count != 0)
        {
            if (debuffList[i].type == Debuff.Type.Stun)
            {
                myStat.MoveSpeed *= StunMoveSpeed;
            }
            else if (debuffList[i].type == Debuff.Type.Slow)
            {
                myStat.MoveSpeed *= SlowMoveSpeed;
            }
            else
            {
                myStat.MoveSpeed = orgMoveSpeed;
            }
        }
    }
}
```

</div>
</details>