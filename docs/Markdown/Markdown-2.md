---
layout: default
title: 두번째
parent: Markdown
nav_order: 2
---

# 마크다운 두번째 사용법 
{: .no_toc }

## 인용문
- `>`로 표현 가능하다.`>>` 두개 쓰면 중첩된 인용문이다. 중첩시킬땐 앞에 스페이스바 2번해서 공간을 줘야한다!  
```
> 이건 인용문이에요.
  >> 이건 인용문 속 인용문이에요.
```
> 이건 인용문이에요.
  >> 이건 인용문 속 인용문이에요.

- `<cite> ---` 태그와 `{{: .small}}`를 함께 써서 인용문 출처도 남길 수 있다.  
```
<cite>Steve Jobs</cite> --- Apple Worldwide Developers' Conference, 1997
{: .small}
```
<cite>Steve Jobs</cite> --- Apple Worldwide Developers' Conference, 1997
{: .small}