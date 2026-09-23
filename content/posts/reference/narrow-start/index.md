---
title: "00. 여기서 시작: 글머리와 기능 안내"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "00. 여기서 시작: 글머리와 기능 안내 — 직접 눌러 보고 소스를 복사하는 Narrow 사용 예제."
categories: [Narrow 사용법]
tags: [narrow, example]
series: [Narrow 실습]
series_order: 0
toc:
  enabled: true
  position: center
license:
  show: true
  author: palilo
  displayName: "예제 표시"
  url: ""
  description: "라이선스 카드의 모양을 확인하는 예시입니다."
---

이 예제는 현재 설치된 **Narrow v1.3.16**의 템플릿을 기준으로 작성했습니다.
아래 링크를 순서대로 열고, 해당 글의 `index.md`와 화면을 비교하세요.
모든 예시 글은 `draft: true`로 Git에 보관하되 일반 배포에서는 제외합니다.
로컬에서 예제를 보려면 `hugo server -D`로 실행하세요.
본문의 작성 예시에 나오는 `draft: false`는 실제로 공개할 글을 위한 설정입니다.

<!-- markdownlint-configure-file {"MD013": {"tables": false}} -->

## 예제 목차

| 글                                                             | 확인할 기능                                    |
| -------------------------------------------------------------- | ---------------------------------------------- |
| [01. Markdown](/posts/reference/narrow-markdown/)              | 제목, 강조, 목록, 표, 각주, 확장 문법          |
| [02. 알림](/posts/reference/narrow-alerts/)                    | 다섯 종류 알림, 접기, HTML details             |
| [03. 코드와 수식](/posts/reference/narrow-code/)               | 코드 복사·접기, 탭, KaTeX, Mermaid             |
| [04. 이미지](/posts/reference/narrow-images/)                  | 표지, 썸네일, 캡션, 세 가지 갤러리, 라이트박스 |
| [05. 숏코드](/posts/reference/narrow-shortcodes/)              | 아이콘, 버튼, 링크 카드, 동영상                |
| [06. 레이아웃과 사이트 기능](/posts/reference/narrow-layouts/) | Timeline, Resume, About, Project와 사이트 설정 |

## 글머리의 구성

[07. 기본 글머리](/posts/reference/narrow-plain/)에서는 표지·요약·시리즈를 모두
생략한 형태를 비교할 수 있습니다.

지금 보이는 제목은 `title`, 제목 아래 소개는 `summary`입니다.
날짜·읽기 시간·글자 수·분류가 기본 정보 카드에 나옵니다.
오른쪽의 시리즈 목록은 같은 `series`를 가진 글을
`series_order` 순으로 묶은 것입니다. 좁은 화면에서는 세로로 배치됩니다.

```yaml
---
title: "나의 새 글"
date: 2026-09-22T09:00:00+09:00
draft: false
description: "검색 엔진 등에 사용하는 설명"
summary: "제목 아래와 목록에 표시할 요약"
categories: [개발]
tags: [hugo, markdown]
series: [나의 연재]
series_order: 1
cover: cover.svg
---
```

Narrow에는 Blowfish의 hero 스타일 선택 옵션이 없습니다.
이 버전의 일반 글은 같은 템플릿을 사용하며 `cover` 유무,
`summary` 유무, `series` 유무로 구성이 달라집니다.
이 글에는 표지가 없고, 이미지 예제에는 표지가 있습니다.

기본 글머리에 작성자 이름이 별도로 나오지는 않습니다.
아래 저작권 카드의 작성자는 `license.author`로 설정할 수 있습니다.
홈 프로필의 작성자는 `hugo.yaml`의 `params.author`입니다.

## 목차와 제목 링크

`##`, `###` 제목이 목차에 반영됩니다.
제목 옆 링크 아이콘으로 해당 문단의 주소를 얻을 수 있습니다.
이 글은 가운데 목차, 코드 예제는 고정 사이드 목차입니다.

```yaml
toc:
  enabled: true
  position: side
  pinned: true
```

목차가 필요 없다면 글의 머릿말에 `toc: false`를 적습니다.
사이드 고정 목차는 화면이 충분히 넓을 때 보입니다.

## 글을 만드는 위치

```text
content/posts/my-post/
  index.md
  cover.svg
```

폴더와 `index.md`를 사용하는 구조를 leaf bundle이라고 합니다.
같은 폴더의 이미지에는 `cover.svg`처럼 상대 경로를 사용하세요.
`draft: true`이면 일반 빌드에서 제외되고 `hugo server -D`에서 보입니다.
미래 날짜의 글도 일반 빌드에서는 제외될 수 있습니다.

## 글 아래 기능

마지막까지 내려가면 저작권, 이전·다음 글, 관련 글을 확인할 수 있습니다.
예제들은 공통 태그를 사용하므로 관련 글을 연결하기 좋습니다.
저작권 카드는 아래 설정을 사용했습니다.
이는 이 예제의 표시 설명이며 실제 라이선스를 새로 선언하지 않습니다.

```yaml
license:
  show: true
  author: palilo
  displayName: "예제 표시"
  url: ""
  description: "라이선스 카드의 모양을 확인하는 예시입니다."
```
