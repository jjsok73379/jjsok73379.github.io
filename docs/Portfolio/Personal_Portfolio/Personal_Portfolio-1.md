---
layout: default
title: 타이틀 캐릭터
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 1
---

# 타이틀 캐릭터  
{: .no_toc }

- 카메라를 하나 추가해 캐릭터를 찍게 했고 RenderTexture로 만들어 UI에 추가했습니다.  
- IPointerEnterHandler와 IPointerExitHandler를 사용해서 캐릭터가 걷는 애니메이션을 합니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public class TitleButtons : MonoBehaviour, IPointerEnterHandler, IPointerExitHandler
{
    [SerializeField]
    GameObject theCharacter;

    public void OnPointerEnter(PointerEventData eventData)
    {
        theCharacter.GetComponent<Animator>().SetBool("Run", true);
    }

    public void OnPointerExit(PointerEventData eventData)
    {
        if (theCharacter.gameObject.IsDestroyed())
        {
            return;
        }
        theCharacter.GetComponent<Animator>().SetBool("Run", false);
    }
}
```

</div>
</details>