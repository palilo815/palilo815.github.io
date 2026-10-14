---
title: "01. Markdown 문법 둘러보기"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "01. Markdown 문법 둘러보기 — 직접 눌러 보고 소스를 복사하는 Narrow 사용 예제."
categories: [Narrow 사용법]
tags: [narrow, example]
series: [Narrow 실습]
series_order: 1
---

소스에서 기호를 확인하고 화면의 결과와 비교하세요.
본문의 최상위 제목은 보통 `##`부터 시작합니다.
페이지의 `title`이 이미 `h1`이기 때문입니다.

## 제목 2단계

### 제목 3단계

#### 제목 4단계

##### 제목 5단계

###### 제목 6단계

같은 방식으로 `# 제목`은 1단계 제목이지만 이 글에서는 중복하지 않았습니다.

## 글자 꾸미기

**굵게**, _기울임_, **_굵은 기울임_**, ~~취소선~~, `인라인 코드`.
==형광펜==, ++삽입 표시++, H~2~O, x^2^도 확인하세요.
이모지는 :smile: :rocket: 또는 🙂처럼 쓸 수 있습니다.

```markdown
**굵게**, _기울임_, **_굵은 기울임_**, ~~취소선~~, `인라인 코드`
==형광펜==, ++삽입 표시++, H~2~O, x^2^
```

형광펜·삽입·아래첨자·위첨자는 이번에 켠 Goldmark extras 확장입니다.
기본 strikethrough 확장은 단일 물결표도 취소선으로 처리하므로 껐습니다.
취소선은 extras.delete가, 아래첨자는 extras.subscript가 처리합니다.
이모지 별칭은 `enableEmoji: true`를 사용합니다.

## 문단과 줄바꿈

빈 줄로 문단을 구분합니다.
소스의 단순 줄바꿈은 보통 같은 문단으로 합쳐집니다.

이것은 새로운 문단입니다.\
문장 끝 역슬래시를 쓰면 같은 문단에서 강제로 줄을 바꿉니다.

## 목록

- 순서 없는 항목
- 또 다른 항목
  - 중첩 항목
  - 중첩 항목 두 번째

1. 글 작성
2. 미리 보기
3. 배포

- [x] 예제 읽기
- [ ] 새 글 써 보기

체크박스는 진행 상황을 표시하는 정적인 목록입니다.

## 정의 목록

Front matter
: 파일 맨 위의 YAML 설정 영역입니다.

Shortcode
: 테마나 Hugo가 제공하는 기능을 호출하는 짧은 문법입니다.

## 표와 정렬

| 왼쪽   | 가운데  | 오른쪽 |
| :----- | :-----: | -----: |
| 문자열 |  상태   |   숫자 |
| Hugo   | 사용 중 |      1 |
| Narrow | 사용 중 |      2 |

## 인용과 구분선

> 짧고 명확한 글이 읽기 좋습니다.
>
> > 인용 안에 인용도 넣을 수 있습니다.

---

가로 구분선은 별도 줄의 `---`로 만듭니다.

## 링크와 각주

[내부 링크](/posts/reference/narrow-start/)는 같은 사이트로 이동합니다.
[외부 링크](https://gohugo.io/)에는 Narrow가 외부 링크 표시를 붙입니다.
[참조형 링크][hugo]도 사용할 수 있습니다.

각주는 본문 설명을 분리할 때 좋습니다.[^memo]

[hugo]: https://gohugo.io/

[^memo]: 이 문장은 각주입니다. 돌아가기 링크도 확인해 보세요.

## HTML 요소

<!-- markdownlint-disable MD033 -->

<kbd>Ctrl</kbd> + <kbd>C</kbd>는 키보드 키 모양입니다.
<abbr title="HyperText Markup Language">HTML</abbr>에는 설명을 붙일 수 있습니다.

<!-- markdownlint-enable MD033 -->

```html
<kbd>Ctrl</kbd> + <kbd>C</kbd>
<abbr title="HyperText Markup Language">HTML</abbr>
```

HTML 요소는 `markup.goldmark.renderer.unsafe: true`로 활성화했습니다.
이 설정은 본문의 HTML을 그대로 출력하므로 직접 관리하는 글에 사용하세요.
