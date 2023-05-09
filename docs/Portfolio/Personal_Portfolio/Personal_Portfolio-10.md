---
layout: default
title: 스킬 합성
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 10
---

# 스킬 합성  
{: .no_toc }

- 스킬과 재료를 확인해서 해당하는 합성된 스킬이 나오게 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public void CombineSkill()
{
    if (CombineSkillSlot.mySkillData == null || CombineMaterialSlot.mySkillData == null) return;
    for (int i = 0; i < CombinedSkills.Length; i++)
    {
        if (CombinedSkills[i].Materials[0] == CombineSkillSlot.mySkillData && CombinedSkills[i].Materials[1] == CombineMaterialSlot.mySkillData)
        {
            myCombinedSkill.GetComponent<CombinedSkill>().mySkillData = CombinedSkills[i];
            myCombinedSkill.GetComponent<Image>().sprite = CombinedSkills[i].myImage;
            myCombinedSkillText.SetActive(false);
        }
    }
    CombineSkillSlot.myImage.sprite = CombineSkillSlot.orgImage;
    CombineMaterialSlot.myImage.sprite = CombineMaterialSlot.orgImage;
    CombineSkillSlot.myText.SetActive(true);
    CombineMaterialSlot.myText.SetActive(true);
}
```

</div>
</details>