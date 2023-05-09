---
layout: default
title: Teleport 이동
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 6
---

# Teleport 이동  
{: .no_toc }

- 내비게이션을 사용해 Warp 함수를 사용했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
void Teleport(GameObject host, int num, bool chk)
{
    if (chk)
    {
        host.GetComponent<ADNpc>().AI_Per.SetActive(true);
        if (host.GetComponent<ADNpc>().myStat.npcJob == CharState.NPCJOB.ACHER)
        {
            host.GetComponent<Host>().myBow.SetActive(true);
        }
    }
    host.GetComponent<NavMeshAgent>().Warp((questchk ? QuestPos1[num] : QuestPos2[num]).transform.position);
    if (host.GetComponent<QuestInformation>().myQuest.questname == "채집")
    {
        host.GetComponent<Host>().StateFarming();
    }
}
```

````c#
public void Teleport(GameObject host)
{
    host.GetComponent<NavMeshAgent>().Warp(spawnPoints[0].transform.position);
    host.transform.parent = spawnPoints[0].transform;
}
````

</div>
</details>