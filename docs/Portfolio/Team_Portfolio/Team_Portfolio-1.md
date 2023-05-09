---
layout: default
title: 스폰매니저
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 1
---

# 스폰매니저  
{: .no_toc }

- 최대 수를 정해줘서 일정 수 이상이 되면 더 이상 스폰 되지 않게 해주었고 마감시간을 넘어가도 스폰이 불가능하게 해주었습니다.  
- 하루가 지나면 시간을 다시 0으로 초기화해주었습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
void Update()
{
    EndTime += Time.deltaTime;
    if (EndTime < TimeManager.Instance.DeadLine)
    {

        if (BlockChk == false) // Npc 생성위치에 아무런 방해물이 없어서 정상일 때
        {
            if (curTime >= spawnTime && hostCount < maxCount)
            {
                Addvlnpc(); // 가중치 값 세팅
                if (first)
                {
                    for (int i = 0; i < vlnpcs.Count; i++)
                    {
                        total += vlnpcs[i].weight;
                    }
                    first = false;
                }
                SpawnHost(); // 콜라이더에서 불값을 전달하고 이프문에서 불값을 검사함
            }
        }
    }

    curTime += Time.deltaTime;
    if (EndTime >= TimeManager.Instance.OneDay)
    {
        QuestManager.Instance.EndQuestClear();
        EndTime = 0.0f;
        curTime = 0.0f;
    }
}
```

</div>
</details>