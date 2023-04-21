---
layout: default
title: 접기 / 펼치기
parent: 마크다운
nav_order: 11
---

# 접기 / 펼치기  
{: .no_toc }

HTML의 `details`태그로 사용 가능하다. `div markdown= " 1 " `은 jekyll에서 html사이에 markdown을 인식하기 위한 코드이다.[참고블로그](https://inasie.github.io/it%EC%9D%BC%EB%B0%98/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4-expander-control/)  

```
<details>
<summary>여기를 눌러주세요</summary>
<div markdown="1">       

😎숨겨진 내용😎

</div>
</details>
```  

<details>
<summary>여기를 눌러주세요</summary>
<div markdown="1">       

😎숨겨진 내용😎

</div>
</details>