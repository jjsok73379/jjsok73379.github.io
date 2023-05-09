---
layout: default
title: 보스 페이즈
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 12
---

# 보스 페이즈  
{: .no_toc }

- 코루틴으로 자신의 체력을 확인해서 ranAction의 범위를 정하고 ranAction에 따라 어떤 행동을 할 지정하게 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public IEnumerator Think()
{
    yield return new WaitForSeconds(0.5f);

    if (myStat.HP > 7000)
    {
        ranAction = Random.Range(0, 2);
    }
    else if (myStat.HP < 7000 && myStat.HP > 3000)
    {
        ranAction = Random.Range(1, 4);
    }
    else if (myStat.HP < 3000)
    {
        ranAction = Random.Range(2, 5);
    }

    switch (ranAction)
    {
        case 0:
            StartCoroutine(BasicAttack());
            break;
        case 1:
            // 박치기 공격
            StartCoroutine(ClawAttack());
            break;
        case 2:
            // 브레스
            StartCoroutine(FlameAttack());
            break;
        case 3:
            // 메테오
            StartCoroutine(MeteorAttack());
            break;
        case 4:
            // 날아서 브레스
            StartCoroutine(FlyingBreath());
            break;
    }
}

IEnumerator MoveToPos(float AttackRange)
{
    transform.LookAt(myTarget);
    //이동
    Vector3 pos = Vector3.zero;
    Vector3 dir = Vector3.zero;
    dir.Normalize();
    while (Vector3.Distance(pos, transform.position) > AttackRange)
    {
        myAnim.SetBool("IsMoving", true);
        float delta = Time.fixedDeltaTime * myStat.MoveSpeed;
        if (myTarget != null)
        {
            pos = myTarget.position;
        }
        dir = pos - transform.position;
        if (delta > dir.magnitude)
        {
            delta = dir.magnitude;
        }
        dir.Normalize();
        transform.Translate(dir * delta, Space.World);
        yield return new WaitForFixedUpdate();
    }
    myAnim.SetBool("IsMoving", false);
}

IEnumerator BasicAttack()
{
    yield return StartCoroutine(MoveToPos(12.0f));
    myAnim.SetTrigger("Attack");
    yield return new WaitForSecondsRealtime(0.5f);
    StartCoroutine(Think());
}

IEnumerator ClawAttack()
{
    yield return StartCoroutine(MoveToPos(17.0f));
    Regions[0].SetActive(true);
    while (Regions[0].GetComponent<LineRegion>().FillProgress <= 0.99f)
    {
        yield return null;
        Regions[0].GetComponent<LineRegion>().FillProgress += 0.4f * Time.deltaTime;
    }
    myStat.AP = 500f;
    Regions[0].SetActive(false);
    Regions[0].GetComponent<LineRegion>().FillProgress = 0;
    myAnim.SetTrigger("ClawAttack");
    yield return new WaitForSecondsRealtime(3.0f);
    myStat.AP = orgDamage;

    StartCoroutine(Think());
}

public void ClawAttackTarget()
{
    Collider[] list = Physics.OverlapSphere(HitPoint.position, 2, enemyMask);

    if (list.Length > 0)
    {
        foreach (Collider col in list)
        {
            col.GetComponent<IBattle>()?.OnDamage(myStat.AP);
        }
    }
}

IEnumerator FlameAttack()
{
    yield return StartCoroutine(MoveToPos(20.0f));
    Regions[1].SetActive(true);
    while (Regions[1].GetComponent<ArcRegion>().FillProgress <= 0.99)
    {
        yield return null;
        Regions[1].GetComponent<ArcRegion>().FillProgress += 0.3f * Time.deltaTime;
    }
    myStat.AP = 400f;
    Regions[1].SetActive(false);
    Regions[1].GetComponent<ArcRegion>().FillProgress = 0;
    UseFlame();
    myAnim.SetTrigger("FlameAttack");
    yield return new WaitForSecondsRealtime(4.0f);
    myStat.AP = orgDamage;

    StartCoroutine(Think());
}

IEnumerator MeteorAttack()
{
    yield return StartCoroutine(MoveToPos(20.0f));
    myStat.AP = 350f;
    myAnim.SetTrigger("MeteorAttack");
    for (int i = 2; i < Regions.Length;)
    {
        Vector3 pos = Vector3.zero;
        Regions[i].SetActive(true);
        pos.x = Random.Range(-15.0f, 15.0f);
        pos.z = Random.Range(-15.0f, 15.0f);
        pos = transform.position + pos;
        Regions[i].transform.position = pos;
        while (Regions[i].GetComponent<CircleRegion>().FillProgress <= 0.99)
        {
            yield return null;
            Regions[i].GetComponent<CircleRegion>().FillProgress += 0.7f * Time.deltaTime;
            if (Regions[i].GetComponent<CircleRegion>().FillProgress > 0.9)
            {
                Regions[i].GetComponentInChildren<ParticleSystem>().Play();
            }
        }
        Regions[i].GetComponent<CircleRegion>().FillProgress = 0;
        Regions[i].SetActive(false);
        i++;
    }
    yield return new WaitForSecondsRealtime(5.0f);
    myStat.AP = orgDamage;

    StartCoroutine(Think());
}

IEnumerator FlyingBreath()
{
    yield return StartCoroutine(MoveToPos(20.0f));
    myAnim.SetTrigger("FlyFlame");
    myStat.AP = 800f;
    yield return new WaitForSecondsRealtime(5.0f);
    UseFlame();
    yield return new WaitForSecondsRealtime(11.0f);
    myStat.AP = orgDamage;

    StartCoroutine(Think());
}

public void UseFlame()
{
    myEnemys = Physics.OverlapSphere(transform.position, 18.0f, enemyMask);
    float RadianRange = Mathf.Cos((90.0f / 2) * Mathf.Deg2Rad);

    for (int i = 0; i < myEnemys.Length; i++)
    {
        float targetRadian = Vector3.Dot(transform.forward, (myEnemys[i].transform.position - transform.position).normalized);
        if (targetRadian > RadianRange)
        {
            if (myEnemys[i].gameObject.layer == 8)
            {
                myEnemys[i].gameObject.GetComponent<IBattle>()?.OnDamage(myStat.AP);
            }
        }
    }
}
```

</div>
</details>