---
title: "대표 프로젝트 카드 예제"
date: 2026-09-22
draft: true
summary: "홈의 대표 프로젝트 카드와 프로젝트 전용 페이지를 비교하기 위한 가상 예제."
status: completed
tags: [narrow, example, project]
cover: /posts/reference/narrow-images/cover.png
link: /posts/reference/narrow-start/
featured: true
---

이 프로젝트는 실제 작업물이 아닌 테마 화면 예제입니다.
`hugo server -D`에서 홈의 대표 프로젝트 카드, `/projects/` 목록,
이 상세 페이지의 표지·상태·태그·링크 버튼을 비교하세요.

```yaml
featured: true
status: completed
cover: /posts/reference/narrow-images/cover.png
link: /posts/reference/narrow-start/
```

일반 빌드에서는 `draft: true` 때문에 이 페이지와 카드가 모두 빠집니다.
