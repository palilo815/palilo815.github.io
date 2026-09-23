---
title: "레이아웃 예제: About"
draft: true
layout: about
summary: "소개 본문은 카드로, links는 별도의 링크 카드로 표시됩니다."
links:
  - name: 예제 안내
    description: Narrow 기능 실습으로 돌아갑니다.
    url: /posts/reference/narrow-start/
    icon: /images/constellation.svg
---

## 소개

이 페이지는 `layout: about`을 사용합니다.
이 영역 전체가 소개 카드 안에 표시됩니다.

## 링크 데이터

아래 링크 카드는 front matter의 `links` 배열로 만들었습니다.

```yaml
links:
  - name: 예제 안내
    description: 실습으로 돌아갑니다.
    url: /posts/reference/narrow-start/
    icon: /images/constellation.svg
```
