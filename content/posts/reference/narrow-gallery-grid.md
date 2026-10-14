---
title: "08. 격자 갤러리"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "같은 크기의 칸에 이미지를 놓는 grid 갤러리 예제."
tags: [narrow, example, gallery]
series: [Narrow 실습]
series_order: 8
gallery:
  enabled: true
  defaultLayout: grid
  columns: 3
  gap: 12
lightbox:
  enabled: true
---

세 장의 그림을 같은 너비의 칸에 배치합니다. 화면을 좁히면 배치가 어떻게 변하는지 확인하세요.
위의 레이아웃 버튼을 누르면 같은 이미지로 justified·masonry 방식도 비교할 수 있습니다.

![가로 그림](/posts/reference/narrow-images/cover.png "가로 그림")
![세로 그림](/posts/reference/narrow-images/portrait.png "세로 그림")
![정사각형 그림](/posts/reference/narrow-images/square.png "정사각형 그림")

이미지를 누르면 라이트박스가 열립니다. 캡션과 이전·다음 이동도 확인해 보세요.

```yaml
gallery:
  enabled: true
  defaultLayout: grid
  columns: 3
  gap: 12
lightbox:
  enabled: true
```

연속된 이미지 사이에 문장을 넣으면 갤러리가 끊어집니다.
[원래 갤러리 예제](/posts/reference/narrow-images/)에는 justified 시작 상태가 있습니다.
