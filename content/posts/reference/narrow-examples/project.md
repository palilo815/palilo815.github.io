---
title: "레이아웃 예제: Project"
draft: true
type: projects
date: 2026-09-22
summary: "일반 글과 다른 프로젝트 전용 글머리입니다."
status: in_progress
tags: [narrow, example]
cover: /posts/reference/narrow-images/cover.svg
link: /posts/reference/narrow-start/
featured: false
---

## 프로젝트 소개

이 페이지는 가상의 프로젝트입니다. 표지, 상태 배지와 프로젝트 링크를 확인하세요.

```yaml
type: projects
status: in_progress
link: /posts/reference/narrow-start/
featured: false
```

상태는 `completed`, `in_progress`와 그 외 값에 따라 표시가 달라집니다.
일반적으로 프로젝트는 `content/projects/` 아래에 작성하며,
이 샘플은 별도 폴더에서 `type: projects`로 같은 템플릿을 선택합니다.

## 구현 범위

- 표지 이미지
- 프로젝트 소개
- 상태와 태그
- 프로젝트 이동 링크
