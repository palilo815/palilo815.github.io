---
title: "05. 아이콘·버튼·링크 카드·동영상"
date: 2026-09-22T09:00:00+09:00
draft: true
summary: "05. 아이콘·버튼·링크 카드·동영상 — 직접 눌러 보고 소스를 복사하는 Narrow 사용 예제."
categories: [Narrow 사용법]
tags: [narrow, example]
series: [Narrow 실습]
series_order: 5
---

Narrow가 직접 제공하는 숏코드는 총 7개입니다:
`icon`, `button`, `link`, `tabs`, `tab`, `bilibili`, `tencent`.
탭 2개는 [코드 예제](/posts/reference/narrow-code/)에서 확인할 수 있습니다.

## 아이콘

{{< icon name="github" size="xs" >}}
{{< icon name="github" size="sm" >}}
{{< icon name="github" size="md" >}}
{{< icon name="github" size="lg" >}}
{{< icon name="github" size="xl" >}}
{{< icon name="github" size="2xl" >}}
{{< icon name="codeforces" size="xl" >}}

```text
{{</* icon name="github" size="lg" */>}}
{{</* icon name="codeforces" size="xl" */>}}
```

아이콘 이름은 `assets/icons/`의 SVG 파일명입니다.
위 마지막 아이콘은 이 사이트에 추가했던 Codeforces 아이콘입니다.
`class="text-primary"`로 테마 강조색을 적용할 수도 있습니다.

## 버튼 색상과 크기

{{< button text="Primary / small" url="/posts/" size="sm" />}}
{{< button text="Secondary / medium" url="/posts/" variant="secondary" />}}
{{< button text="Outline / large" url="/posts/" variant="outline" size="lg" />}}
{{< button text="커스텀 색상" url="/posts/" variant="#7c3aed" />}}
<!-- markdownlint-disable MD034 -->

{{< button text="GitHub 새 창"
  url="https://github.com/palilo815" icon="github" target="_blank" />}}

<!-- markdownlint-enable MD034 -->

```text
{{</* button text="글 목록" url="/posts/" variant="outline" size="lg" /*/>}}
{{</* button url="/posts/" */>}}본문으로 버튼 이름 지정{{</* /button */>}}
```

`variant`는 primary·secondary·outline·색상 코드,
`size`는 sm·md·lg입니다. `target`의 기본값은 `_self`입니다.
URL을 생략하면 이동 동작 없는 일반 버튼이 됩니다.

## 직접 지정하는 링크 카드

<!-- markdownlint-disable MD034 -->

{{< link title="내 GitHub" description="직접 입력한 링크 카드 예시"
  url="https://github.com/palilo815" icon="/images/constellation.svg" >}}

<!-- markdownlint-enable MD034 -->

```text
{{</* link title="내 GitHub" description="소개"
  url="https://github.com/palilo815" icon="/images/constellation.svg" */>}}
```

## 데이터 파일을 사용하는 링크 카드

아래 카드는 `data/links/narrow_examples.yaml`의 데이터를 읽습니다.

{{< link id="narrow-example-guide" >}}

그룹 전체를 출력할 수도 있습니다.

{{< link category="narrow_examples" >}}

```text
{{</* link id="narrow-example-guide" */>}}
{{</* link category="narrow_examples" */>}}
```

`ref`는 `id`의 별칭, `group`은 `category`의 별칭입니다.

## 동영상 임베드

동영상 플레이어는 외부 서비스에 연결됩니다.
아래는 숏코드가 만드는 실제 프레임입니다.
영상 공개 여부·지역·네트워크에 따라 재생이 제한될 수 있습니다.

### Bilibili

{{< bilibili BV1GJ411x7h7 >}}

```text
{{</* bilibili BV1GJ411x7h7 */>}}
{{</* bilibili av170001 1 */>}}
```

첫 번째 인수는 BV 또는 av ID, 두 번째 인수는 분할 영상의 번호입니다.

### Tencent

{{< tencent x0036v1m81n >}}

```text
{{</* tencent x0036v1m81n */>}}
```

위 ID는 플레이어 형태를 보는 샘플 값입니다.
실제 글에서는 공개된 Tencent 영상의 `vid`로 교체하세요.
동영상 자체의 재생 성공 여부는 검증하지 않았습니다.

## Hugo 내장 숏코드와 구별하기

`ref`, `relref`, `figure`, `highlight`, `youtube` 등은
Narrow 전용이 아니라 Hugo 자체의 기능입니다.
이 페이지는 Narrow의 일곱 숏코드를 모두 다룹니다.
설치된 Hugo 버전에 따라 내장 숏코드 목록은 달라질 수 있습니다.
