---
layout: default
title: AI 자동전투
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 4
---

# AI 자동전투  
{: .no_toc }

- 직업별로 공격이 다르게 했습니다.  
- 적을 찾으면 유한 상태기 계 STATE를 Battle로 바꾸어주었고 적이 죽어서 없어지면 Idle 상태로 변하게 해주었습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
IEnumerator AttackingTarget(Transform target, float AttackRange, float AttackDelay)
{
    float playTime = 0.0f;
    float delta = 0.0f;
    while (target != null)
    {
        if (!_anim.GetBool("IsAttacking")) playTime += Time.deltaTime;
        Vector3 dir = target.position - transform.position;
        float dist = dir.magnitude;
        if (dist > myStat.AttackRange)
        {
            _anim.SetBool("IsMoving", true);
            dir.Normalize();
            delta = myStat.MoveSpeed * Time.deltaTime;
            if (delta > dist)
            {
                delta = dist;
            }
            transform.Translate(dir * delta, Space.World);
        }
        else
        {
            _anim.SetBool("IsMoving", false);
            if (playTime >= myStat.AttackDelay)
            {
                playTime = 0.0f;

                switch (_adnpc.adtype)//직업별 애니메이션 실행
                {
                    case 0: // 여자 궁수
                        _anim.SetTrigger("ArrowAttack");
                        CreateArrow();
                        break;
                    case 1: // 여자 도적
                        _anim.SetTrigger("ThiefAttack");
                        break;
                    case 2: // 여자 마법사
                        _anim.SetTrigger("MagicAttack");
                        break;
                    case 3: // 남자 궁수
                        _anim.SetTrigger("ArrowAttack");
                        CreateArrow();
                        break;
                    case 4: // 남자 도적
                        _anim.SetTrigger("ThiefAttack");
                        break;
                    case 5: // 남자 마법사
                        _anim.SetTrigger("MagicAttack");
                        break;
                    case 6: // 남자 전사
                        _anim.SetTrigger("WarriorAttack");
                        break;
                }
            }
        }
        delta = myStat.RotSpeed * Time.deltaTime;
        float Angle = Vector3.Angle(dir, transform.forward);
        float rotDir = 1.0f;
        if (Vector3.Dot(transform.right, dir) < 0.0f)
        {
            rotDir = -rotDir;
        }
        if (delta > Angle)
        {
            delta = Angle;
        }
        transform.Rotate(Vector3.up * delta * rotDir, Space.World);
        yield return null;
    }
    _anim.SetBool("IsMoving", false);
}
```

</div>
</details>