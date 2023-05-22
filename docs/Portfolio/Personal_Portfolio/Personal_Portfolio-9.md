---
layout: default
title: 스킬 관리
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 9
---

# 스킬 관리  
{: .no_toc }

- 스킬은 ScritableObject로 관리했습니다.  

<details>
<summary>이미지 보기</summary>
<div markdown="1">

![image](https://user-images.githubusercontent.com/114732330/237050186-53839e2b-5668-45c6-b4e5-0e56f784f865.png)

</div>
</details>  
<details>
<summary>코드 보기</summary>
<div markdown="2">

````c#
[CreateAssetMenu(fileName = "SkillData", menuName = "ScriptableObjects/SkillData", order = 1)]
public class SkillData : ScriptableObject
{
    public enum SkillType
    {
        Ball, Bomb, NonTargeting, Material
    }

    public string SkillName;
    public Sprite myImage = null;
    public int Level;
    public string myInfo;
    [SerializeField] 
    float AttackRange;
    [SerializeField]
    int _mana;
    public float CoolTime;
    [SerializeField]
    float[] skillDamage;
    [SerializeField] int[] MaterialCounts;
    public SkillData[] Materials;
    public GameObject mySkill;
    public SkillType myType;

    public int Mana
    {
        get => _mana;
        set => _mana = value;
    }

    public int GetMaterialCount(int lv)
    {
        return MaterialCounts[lv - 1];
    }

    public int GetMaxLevel()
    {
        return MaterialCounts.Length;
    }

    public float SkillDamage(int lv)
    {
        return skillDamage[lv - 1];
    }

    public string MyInfo
    {
        get => myInfo;
        set => myInfo = value;
    }
}
````

</div>
</details>