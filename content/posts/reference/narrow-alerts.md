---
title: "02. 알림 상자와 접기"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "02. 알림 상자와 접기 — 직접 눌러 보고 소스를 복사하는 Narrow 사용 예제."
categories: [Narrow 사용법]
tags: [narrow, example]
series: [Narrow 실습]
series_order: 2
---

각 상자의 색상은 상단 팔레트와 다크 모드를 바꾸면 함께 달라집니다.

## 다섯 종류의 알림

<!-- markdownlint-disable MD028 -->

> [!NOTE]
> 부연 설명이나 참고 사항입니다.

> [!TIP]
> 알아 두면 유용한 팁입니다.

> [!IMPORTANT]
> 놓치지 말아야 할 핵심 정보입니다.

> [!WARNING]
> 실행 전에 확인할 주의 사항입니다.

> [!CAUTION]
> 특히 신중히 다뤄야 하는 내용입니다.

```markdown
> [!NOTE]
> 참고 사항입니다.

> [!TIP]
> 팁입니다.

> [!IMPORTANT]
> 중요 정보입니다.

> [!WARNING]
> 주의 사항입니다.

> [!CAUTION]
> 경고 내용입니다.
```

<!-- markdownlint-enable MD028 -->

## 펼친 상태로 시작

> [!TIP]+ 클릭하면 접히는 팁
> `+`를 붙이면 처음에는 펼쳐져 있습니다.
>
> - 목록도 넣을 수 있습니다.
> - **강조**와 `코드`도 사용할 수 있습니다.

## 접힌 상태로 시작

> [!NOTE]- 정답 보기
> 정답은 42입니다. 제목을 다시 누르면 접힙니다.

```markdown
> [!TIP]+ 클릭하면 접히는 팁
> 처음에는 펼쳐져 있습니다.

> [!NOTE]- 정답 보기
> 처음에는 접혀 있습니다.
```

## 기본 HTML details

<!-- markdownlint-disable MD033 -->

<details>
<summary>표준 HTML로 만든 접기 영역</summary>

안에 **Markdown**을 넣을 수 있습니다.

- 첫 번째 항목
- 두 번째 항목

</details>

<!-- markdownlint-enable MD033 -->

```html
<details>
  <summary>표시할 제목</summary>

  안에 **Markdown**을 넣습니다.
</details>
```

태그와 본문 사이의 빈 줄을 유지하세요.
이 방식은 Narrow 알림 상자와 별개의 HTML 기능입니다.
