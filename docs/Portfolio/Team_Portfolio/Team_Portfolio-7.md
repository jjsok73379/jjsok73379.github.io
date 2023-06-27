---
layout: default
title: 패널티
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 7
---

# 패널티  
{: .no_toc }

- 퀘스트에 성공하면 돈과 명예가 늘어나고 퀘스트에 실패하면 돈과 명예가 줄어들도록 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public void AddReward()
{
    _childHost.Questing = false;
    Destroy(ChildOBJ.GetComponent<Host>().Quest.gameObject);
    QuestManager.Instance.EndQuest(myQuest);
    if (chk)
    {
        SoundManager.Instance.MoneySound.Play();
        GameManager.Instance.ChangeGold(myQuest.rewardgold);
        GameManager.Instance.ChangeFame(myQuest.rewardfame);
        _childHost.onSmile = true;
    }
    else
    {
        GameManager.Instance.ChangeGold(-myQuest.rewardgold);
        if (SpawnManager.Instance.EndTime >= TimeManager.Instance.DeadLine)
        {
            GameManager.Instance.ChangeFame(-myQuest.rewardfame);
        }
        _childHost.onAngry = true;
    }
    Destroy(gameObject);
}
```

</div>
</details>