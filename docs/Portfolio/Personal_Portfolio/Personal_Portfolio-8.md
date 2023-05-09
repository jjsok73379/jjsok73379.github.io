---
layout: default
title: 콤보 공격
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 8
---

# 콤보 공격  
{: .no_toc }

- 스페이스바를 누르면 기본 공격을 하고 추가로 스페이스바를 누르면 카운트가 누적되어 콤보 공격이 가능하게 했습니다.  
- 스페이스바를 추가로 누르지 않으면 콤보를 멈추도록 했습니다.  
- AnimEvent에 ComboCheck라는 함수를 추가하여 스페이스바가 눌렸는지 확인하게 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public void ComboAttack()
{
    if (Input.GetKeyDown(KeyCode.Space) && !myAnim.GetBool("IsComboAttacking"))
    {
        if (!SkillPrepare)
        {
            SoundManager.Inst.SwordAttackSound.Play();
            myAnim.SetTrigger("ComboAttack");
        }
    }
    if (IsCombable)
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            ++clickCount;
        }
    }
}

public void ComboAttackTarget()
{
    Collider[] list = Physics.OverlapSphere(AttackPoint.position, 1f, enemyMask);

    if (list.Length > 0)
    {
        foreach (Collider col in list)
        {
            col.GetComponent<IBattle>()?.OnDamage(myStat.AttackDamage);
        }
    }
}

public void ComboCheck(bool v)
{
    if (v)
    {
        IsCombable = true;
        clickCount = 0;
    }
    else
    {
        IsCombable = false;
        if (clickCount == 0)
        {
            myAnim.SetTrigger("ComboFail");
        }
    }
}
```

````c#
public class AnimEvent : MonoBehaviour
{
    public UnityEvent<bool> ComboCheck = default;

    public void ComboCheckStart()
    {
        ComboCheck?.Invoke(true);
    }

    public void ComboCheckEnd()
    {
        ComboCheck?.Invoke(false);
    }
}
````

</div>
</details>