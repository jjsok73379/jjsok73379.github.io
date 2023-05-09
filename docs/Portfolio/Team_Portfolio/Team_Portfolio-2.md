---
layout: default
title: 사운드
parent: 팀 포트폴리오
grand_parent: 포트폴리오
nav_order: 2
---

# 사운드  
{: .no_toc }

- slider 값으로 사운드를 조절했습니다.  
- PlayerPrefs를 사용해서 볼륨 크기를 저장하고 다른 씬에서 저장한 볼륨 크기를 가져옵니다.  

<details>
<summary>코드 보기</summary>
<div markdown="1">

```c#
public class SoundManager : Singleton<SoundManager>
{
    public AudioSource BGMSound;
    public AudioSource[] Eff;

    private void Start()
    {
        Scene scene = SceneManager.GetActiveScene();
        if (scene.name == "Tutorial1")
        {
            SoundList.volume = PlayerPrefs.GetFloat("volume");
        }
        else
        {
            BGMSound.volume = PlayerPrefs.GetFloat("volume");
        }
        foreach (AudioSource source in Eff)
        {
            source.volume = PlayerPrefs.GetFloat("eff");
        }
    }
}
```

````c#
public void SetVolume()
{
    PlayerPrefs.SetFloat("volume", BGMvolume.value);
    BGM.volume = PlayerPrefs.GetFloat("volume");
    PlayerPrefs.SetFloat("eff", Effvolume.value);
    foreach (AudioSource source in Eff)
    {
        source.volume = PlayerPrefs.GetFloat("eff");
    }
}
````

</div>
</details>