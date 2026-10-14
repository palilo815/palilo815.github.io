---
title: "10. 이미지 단독 표시"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "갤러리와 라이트박스를 끈 일반 이미지 표시 예제."
categories: [Narrow 사용법]
tags: [narrow, example, image]
series: [Narrow 실습]
series_order: 10
gallery:
  enabled: false
lightbox:
  enabled: false
---

이 글의 그림에는 갤러리 레이아웃 버튼과 클릭 확대가 붙지 않습니다.
[갤러리 예제](/posts/reference/narrow-images/)와 비교해 보세요.

![가로 그림](/posts/reference/narrow-images/cover.png "첫 번째 그림")
![세로 그림](/posts/reference/narrow-images/portrait.png "두 번째 그림")

```yaml
gallery:
  enabled: false
lightbox:
  enabled: false
```

두 설정은 글마다 따로 조정할 수 있습니다. 예를 들어 갤러리만 끄고
라이트박스는 켜면 각 이미지를 개별적으로 확대할 수 있습니다.
