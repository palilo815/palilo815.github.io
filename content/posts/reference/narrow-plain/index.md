---
title: "07. 기본 글머리: 표지와 시리즈 없이"
date: 2026-09-22T09:00:00+09:00
draft: true
tags: [narrow, example]
toc: false
license:
  show: false
---

이 글은 비교용으로 표지, 요약, 시리즈, 목차, 저작권 카드를 생략했습니다.
제목과 날짜·읽기 시간·글자 수·태그만 있는 기본 글머리를 확인하세요.

## 최소 설정

```yaml
---
title: "나의 글"
date: 2026-09-22
draft: false
tags: [narrow, example]
toc: false
license:
  show: false
---
```

[표지가 있는 글](/posts/reference/narrow-images/),
[시리즈가 있는 글](/posts/reference/narrow-start/)과 비교하면 차이가 분명합니다.
이 예제는 시리즈 없는 모습을 보여 주기 위해 연재 목록에 넣지 않았습니다.

## 직접 바꿔 보기

이 파일에 `summary: "짧은 소개"`를 추가하면 제목 아래에 요약이 나타납니다.
`series: [Narrow 실습]`을 추가하면 시리즈 영역이 생깁니다.
표지가 필요하면 같은 폴더에 이미지를 넣고 `cover`에 파일명을 적으세요.
