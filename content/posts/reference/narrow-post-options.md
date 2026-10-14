---
title: "12. 글 정보와 저작권 카드"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "글머리의 태그·시리즈와 글 아래 저작권 카드 표시를 비교하는 예제."
description: "Narrow 글 정보 표시 예제"
tags: [narrow, example, metadata]
series: [Narrow 실습]
series_order: 12
toc: false
license:
  show: false
---

제목 아래에서 날짜, 읽기 시간, 글자 수, 태그와 시리즈 목록을 확인하세요.
`summary`는 제목 바로 아래에 보이고, `description`은 검색 엔진용 메타데이터에 쓰입니다.

## 아래쪽에서 비교하기

이 글은 `license.show: false`라 저작권 카드가 없습니다.
[첫 예제](/posts/reference/narrow-start/)는 카드가 보입니다.
목차도 `toc: false`로 껐으므로 제목은 있지만 목차 패널은 없습니다.

```yaml
summary: "제목 아래 요약"
description: "검색 엔진용 설명"
tags: [narrow, example]
series: [Narrow 실습]
series_order: 12
toc: false
license:
  show: false
```

상단의 태그·시리즈를 눌러 목록 화면으로 이동해 보세요.
하단에는 이전·다음 글과 관련 글이 표시됩니다.
