---
layout: default
title: 줄세우기
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 5
---

# 줄세우기  
{: .no_toc }

- 앞에 사람이 있을 경우 멈추고 사람이 앞에서 비키면 다시 이동한다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
IEnumerator ForwardCheck()// 앞에 누가있는지 구분하여 상태를 Wait 또는 Order로 바꿔줌
{
    while (true)
    {
        if (Physics.SphereCast(transform.position, 7.0f, transform.forward, out RaycastHit hitinfo, 7.0f, layerMask))
        {
            agent.ResetPath();
            agent.velocity = Vector3.zero;
            _anim.SetBool("IsMoving", false);

            if (hitinfo.collider.gameObject.layer == 6)
            {
                if (hitinfo.collider.gameObject.GetComponent<Host>().LineChk == true)
                {
                    LineChk = true;
                }
                ChangeState(STATE.Wait);
            }
            else
            {
                myStaff = hitinfo.collider.gameObject;
                ChangeState(STATE.Order);
            }
        }
        else
        {
            ChangeState(STATE.Moving);
        }
        yield return null;
    }
}
```

</div>
</details>