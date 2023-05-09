---
layout: default
title: 몬스터 스폰
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 6
---

# 몬스터 스폰  
{: .no_toc }

- 몬스터의 최대수를 정해주고 리스트의 수보다 적어지면 새로운 몬스터를 스폰 하게 했습니다. 일정 구간을 정해 겹쳐서 생성되지 않게 랜덤 함수를 사용했습니다.  
- 몬스터가 죽으면 null이 되고 리스트에서 제거합니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public class Spawner : MonoBehaviour
{
    public GameObject orgMonster;
    List<GameObject> list = new List<GameObject>();
    [SerializeField]
    Vector3 pos;
    [SerializeField]
    int CountNum;

    void Update()
    {
        if(list.Count < CountNum)
        {
            pos.x = Random.Range(pos.x - 3.0f, pos.x + 3.0f);
            pos.y = 1.0f;
            pos.z = Random.Range(pos.z - 3.0f, pos.z + 3.0f);
            Vector3 rot = Vector3.zero;
            rot.y = Random.Range(0.0f, 360.0f);
            GameObject obj = Instantiate(orgMonster, pos, Quaternion.Euler(rot), transform);
            list.Add(obj);
        }

        for(int i = 0; i < list.Count;)
        {
            if(list[i] == null)
            {
                list.RemoveAt(i);
                continue;
            }
            ++i;
        }
    }
}
```

</div>
</details>