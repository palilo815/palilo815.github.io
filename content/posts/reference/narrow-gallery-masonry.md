---
title: "09. 벽돌 갤러리"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "가로·세로 그림의 비율을 살리는 masonry 갤러리 예제."
categories: [Narrow 사용법]
tags: [narrow, example, gallery]
series: [Narrow 실습]
series_order: 9
gallery:
  enabled: true
  defaultLayout: masonry
  columns: 2
  columnWidth: 220
  gap: 14
lightbox:
  enabled: true
---

높이가 다른 그림을 벽돌처럼 배치합니다. [격자 갤러리](/posts/reference/narrow-gallery-grid/)와
비교하면 세로 그림의 비율이 더 잘 드러납니다.

![세로 그림](/images/reference/portrait.png "세로형")
![가로 그림](/images/reference/cover.png "가로형")
![정사각형 그림](/images/reference/square.png "정사각형")
![세로 그림 반복](/images/reference/portrait.png "같은 그림도 다른 자리에 배치됩니다")

```yaml
gallery:
  enabled: true
  defaultLayout: masonry
  columns: 2
  columnWidth: 220
  gap: 14
```

레이아웃 전환 버튼으로 grid와 justified도 눌러 보세요.
사진 비율, 화면 너비, `columns` 값에 따라 최종 배치는 달라집니다.
