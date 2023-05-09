---
layout: default
title: 가중치랜덤
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 3
---

# 가중치랜덤  
{: .no_toc }

- 처음에는 일반 시민만 스폰이 되게 하고 명성이 높아지고 일반 시민이 스폰 될수록 귀족이 스폰 될 확률이 올라가고 더 진행할수록 왕족의 스폰 확률을 높였습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public static int W_Random(Quest.QuestGRADE[] RandomSet)
{
    int Lenght = RandomSet.Length;
    int fame = GameManager.Instance.Fame;
    int[] weights = new int[Lenght];

    switch (Lenght)
    {
        case 3:
            {
                if (fame >= 0)
                {
                    weights[0] = 100;
                    weights[1] = 0;

                    for (int i = 0; i < (fame / 1000); i++)
                    {
                        if (weights[0] != 0)
                        {
                            weights[0] -= (int)0.5f;
                            weights[1] += ((weights[1] >= 20) ? (int)0.4f : (int)0.5f);
                        }
                        else
                        {
                            if (weights[1] != 0)
                            {
                                weights[1] -= (int)0.4f;
                            }
                            else if (weights[1] == 0)
                            {
                                break;
                            }
                        }
                    }
                    weights[2] = 100 - (weights[0] + weights[1]);
                }
            }
            break;
        case 2:
            {
                if (fame >= 0)
                {
                    weights[0] = 100;
                    for (int i = 0; i < (fame / 1000); i++)
                    {
                        if (weights[0] == 0)
                        {
                            break;
                        }
                        weights[0] -= (int)0.1f;
                    }
                    weights[1] = 100 - weights[0];
                }
            }
            break;
        case 1:
            {
                weights[0] = 100;
            }
            break;
    }
    int total = 0;
    for (int t = 0; t < weights.Length; ++t)
    { total += weights[t]; }

    int pivot = Mathf.RoundToInt(total * UnityEngine.Random.Range(0.0f, 1.0f));

    for (int n = 0; n < weights.Length; ++n)
    {
        if (pivot <= weights[n])
        {
            return n;
        }
        else
        {
            pivot -= weights[n];
        }
    }
    return 0;
}
```

</div>
</details>