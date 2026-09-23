---
title: "06. 전용 레이아웃과 사이트 기능"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "06. 전용 레이아웃과 사이트 기능 — 직접 눌러 보고 소스를 복사하는 Narrow 사용 예제."
categories: [Narrow 사용법]
tags: [narrow, example]
series: [Narrow 실습]
series_order: 6
---

일반 글과 전용 페이지는 같은 Markdown이라도 레이아웃이 다릅니다.
아래 샘플은 실제 개인 Resume와 분리된 가상 내용입니다.

<!-- markdownlint-configure-file {"MD013": {"tables": false}} -->

## 전용 레이아웃 직접 보기

| 샘플                                                   | 설정               | 특징                          |
| ------------------------------------------------------ | ------------------ | ----------------------------- |
| [Timeline](/posts/reference/narrow-examples/timeline/) | `layout: timeline` | 각 2단계 제목이 타임라인 항목 |
| [Resume](/posts/reference/narrow-examples/resume/)     | `layout: resume`   | 2단계 섹션·3단계 항목 카드    |
| [About](/posts/reference/narrow-examples/about/)       | `layout: about`    | 소개 카드와 링크 목록         |
| [Project](/posts/reference/narrow-examples/project/)   | `type: projects`   | 표지·상태·프로젝트 링크       |

각 샘플은 `content/posts/reference/narrow-examples/`에 있습니다.
일반 프로젝트는 `content/projects/프로젝트명/index.md`에 만들면 됩니다.
`featured: true`로 대표 프로젝트를 지정할 수 있지만,
홈 대표 프로젝트 영역도 별도로 활성화되어 있어야 합니다.

## 목록과 분류

[Posts](/posts/)는 일반 글 목록,
[Archives](/archives/)는 날짜별 글 모음입니다.
[Categories](/categories/), [Tags](/tags/), [Series](/series/)도 확인하세요.
시리즈는 글머리와 분류 화면에서 순서를 확인할 수 있습니다.

목록 페이지는 `_index.md`, 단일 글 묶음은 `index.md`를 사용합니다.
페이지 수가 많아지면 목록에 페이지 나누기가 적용됩니다.

## 사이트 공통 기능

- 상단 팔레트: 현재 등록된 색상 테마 전환
- 해·달 버튼: 밝은 모드와 어두운 모드
- 콘텐츠 너비 버튼: 넓은 화면에서 본문 너비 전환
- 검색: 제목·본문 검색. 검색용 홈 JSON 출력을 이번에 활성화했습니다.
- 읽기 진행 표시와 위로 이동: 긴 글을 스크롤하며 확인
- 이전·다음 글과 관련 글: 일반 글 하단
- [RSS Feed](/index.xml): 새 글 구독용 피드

상단과 하단 UI의 배치는 화면 크기와 테마 설정에 영향을 받습니다.
색상 테마는 개별 글의 Markdown 문법이 아니라 사이트 공통 설정입니다.

## 별도 설정이 필요한 기능

다음은 글만 작성해서 완성되는 기능이 아니므로 실제 서비스를 연결하지 않았습니다.

| 기능                   | 필요한 설정                                                             |
| ---------------------- | ----------------------------------------------------------------------- |
| 언어 전환              | 언어별 사이트 설정과 번역 콘텐츠                                        |
| 댓글                   | Giscus·Disqus·Utterances·Waline·Artalk·Twikoo·Comentario 중 서비스 설정 |
| 방문 통계              | Google·Umami·Clarity·Baidu 등의 계정/서비스 설정                        |
| PWA manifest           | WebAppManifest 출력과 사이트 메타데이터                                 |
| 소셜 공유 미리보기·SEO | 실제 baseURL, 설명, 대표 이미지                                         |

현재 `baseURL`은 `https://example.org/`입니다.
실제 배포에서는 워크플로의 baseURL 재정의 또는 올바른 사이트 주소가 필요합니다.

## 기능을 더 조절하는 곳

`hugo.yaml`의 `params`에서 사이트 공통 설정을 관리합니다.
예를 들어 `toc`, `gallery`, `lightbox`, `katex`, `mermaid`는
개별 글의 front matter에서 적용 범위를 조절할 수 있습니다.

이 시리즈는 v1.3.16의 글쓰기 기능과 전용 페이지를 대상으로 합니다.
모든 Hugo 기능이나 외부 댓글 서비스의 운영 설정을 복제한 것은 아닙니다.
앞으로 테마 버전을 바꾸면 지원 옵션이 달라질 수 있습니다.
