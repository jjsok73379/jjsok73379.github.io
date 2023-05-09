---
layout: default
title: 단축키
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 3
---

# 단축키  
{: .no_toc }

- 각각 단축키를 넣어줘서 해당 창이 열고 닫히는 걸 구현했고 창이 열려있을 때 Esc 버튼을 누르면 모든 창이 꺼지게 했습니다.  
- 다른 창이 열려있으면 IsActive라는 bool 값 함수를 true로 해주고 닫혀있으면 false로 해주었습니다. IsActive가 false 일 때만 설정 창이 켜지게 했습니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public class OpenManager : MonoBehaviour
{
    void Update()
    {
        if (!inventoryActivated && !CharacterInfoActivated && !CombineActivated && !MenuActivated && !SkillActivated)
        {
            IsActive = false;
            if (QuestManager.Inst != null)
            {
                if (QuestActivated)
                {
                    IsActive = true;
                }
                else
                {
                    IsActive = false;
                }
            }
        }
        else
        {
            IsActive = true;
        }
        if (go_Inventory != null)
        {
            if (Input.GetKeyDown(KeyCode.I))
            {
                SoundManager.Inst.OpenWindowSound.Play();
                TryOpenInventory();
            }
            if (inventoryActivated)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    SoundManager.Inst.OpenWindowSound.Play();
                    inventoryActivated = false;
                    go_Inventory.SetActive(false);
                }
            }
            else
            {
                for (int i = 0; i < InventoryManager.Inst.allSlots.Length; i++)
                {
                    if (!InventoryManager.Inst.allSlots[i].isQuickSlot)
                    {
                        ItemEffectDatabase.Inst.HideToolTip();
                    }
                }
            }
        }

        if(CharacterInfo != null)
        {
            if (Input.GetKeyDown(KeyCode.E))
            {
                SoundManager.Inst.OpenWindowSound.Play();
                TryOpenCharacterInfo();
            }
            if (CharacterInfoActivated)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    SoundManager.Inst.OpenWindowSound.Play();
                    CharacterInfoActivated = false;
                    CharacterInfo.SetActive(false);
                }
            }
        }

        if(SkillMenu != null)
        {
            if (Input.GetKeyDown(KeyCode.K))
            {
                SoundManager.Inst.OpenWindowSound.Play();
                TryOpenSkill();
            }
            if (SkillActivated)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    SoundManager.Inst.OpenWindowSound.Play();
                    SkillActivated = false;
                    SkillMenu.SetActive(false);
                }
            }
            else
            {
                SkillManager.Inst.ReinforceOpen = false;
                SkillManager.Inst.ReinforceWindow.SetActive(false);
            }
        }

        if(CombineWindow != null)
        {
            if (Input.GetKeyDown(KeyCode.C))
            {
                SoundManager.Inst.OpenWindowSound.Play();
                TryOpenCombine();
            }
            if (CombineActivated)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    SoundManager.Inst.OpenWindowSound.Play();
                    CombineActivated = false;
                    CombineWindow.SetActive(false);
                }
            }
            else
            {
                SkillManager.Inst.myCombinedSkillText.SetActive(true);
            }
        }

        if(go_Quest != null)
        {
            if (Input.GetKeyDown(KeyCode.Q))
            {
                SoundManager.Inst.OpenWindowSound.Play();
                TryOpenQuestUI();
            }
            if (QuestActivated)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    SoundManager.Inst.OpenWindowSound.Play();
                    QuestActivated = false;
                    go_Quest.SetActive(false);
                }
            }
            else
            {
                if (QuestManager.Inst.objQ2 != null)
                {
                    QuestManager.Inst.objQ2.GetComponent<QuestInfo>().myInfo.SetActive(false);
                }
            }
        }

        if(go_Setting != null)
        {
            if (!IsActive)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    SoundManager.Inst.OpenWindowSound.Play();
                    TryOpenSettingMenu();
                }
            }
            if (SettingActivated)
            {
                Time.timeScale = 0;
            }
            else
            {
                Time.timeScale = 1;
            }
        }

        if (theBossZone != null && thePlayableDirector != null && theBossDragon != null)
        {
            if (theBossZone.IsEnter)
            {
                if (Input.GetKeyDown(KeyCode.Escape))
                {
                    thePlayableDirector.Stop();
                    theBossDragon.gameObject.transform.position = new Vector3(34.8f, 2.1f, 75.3f);
                    theBossDragon.myHPSlider.gameObject.SetActive(true);
                    theBossZone.IsEnter = false;
                }
            }
        }
    }

    public void OpenMenu()
    {
        MenuActivated = !MenuActivated;
        go_Menu.SetActive(MenuActivated);
    }

    public void TryOpenInventory()
    {
        inventoryActivated = !inventoryActivated;
        go_Inventory.SetActive(inventoryActivated);
    }

    public void TryOpenCharacterInfo()
    {
        CharacterInfoActivated = !CharacterInfoActivated;
        CharacterInfo.SetActive(CharacterInfoActivated);
    }

    public void TryOpenSkill()
    {
        SkillActivated = !SkillActivated;
        SkillMenu.SetActive(SkillActivated);
    }

    public void TryOpenCombine()
    {
        CombineActivated = !CombineActivated;
        CombineWindow.SetActive(CombineActivated);
    }

    public void TryOpenQuestUI()
    {
        QuestActivated = !QuestActivated;
        go_Quest.SetActive(QuestActivated);
    }

    public void TryOpenSettingMenu()
    {
        SettingActivated = !SettingActivated;
        go_Setting.SetActive(SettingActivated);
    }

    public void TryOpenSoundWindow()
    {
        SoundActivated = !SoundActivated;
        go_Sound.SetActive(SoundActivated);
    }
}

```

</div>
</details>