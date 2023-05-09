---
layout: default
title: 사운드
parent: 개인 포트폴리오
grand_parent: 포트폴리오
nav_order: 2
---

# 사운드  
{: .no_toc }

- audiomixer를 사용해 slider의 값으로 사운드를 조절했습니다.  
- PlayerPrefs를 사용해서 slider의 값을 저장하고 다른 씬에서 저장한 slider의 값을 가져옵니다.

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public void SetBgmVolume()
{
    audioMixer.SetFloat("BGM", Mathf.Log10(BgmSlider.value) * 20);
}

public void SetSfxVolume()
{
    audioMixer.SetFloat("SFX", Mathf.Log10(SfxSlider.value) * 20);
}

public void CloseWindow()
{
    PlayerPrefs.SetFloat("BgmVolume", BgmSlider.value);
    BgmSlider.value = PlayerPrefs.GetFloat("BgmVolume");
    PlayerPrefs.SetFloat("SfxVolume", SfxSlider.value);
    SfxSlider.value = PlayerPrefs.GetFloat("SfxVolume");
}
```

````c#
public class SoundManager : MonoBehaviour
{
    void Start()
    {
        soundOption.BgmSlider.value = PlayerPrefs.GetFloat("BgmVolume");
        soundOption.SfxSlider.value = PlayerPrefs.GetFloat("SfxVolume");
        BGM.Play();
    }
}
````

</div>
</details>