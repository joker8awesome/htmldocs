# CLAUDE.md — HTML Docs 저장소 규칙

이 저장소는 주제별 정리를 자기완결형 단일 .html 파일로 축적하는 개인 문서 허브다.
GitHub Pages로 서빙된다. 답변은 한국어로, 간결하게.

## 핵심 워크플로 (문서 추가 요청 시 항상 이 순서로)

사용자가 "X를 문서로 정리해줘" / "이 대화 내용 올려줘" 라고 하면:

1. `docs/YYYYMMDD-주제.html` 파일 생성 (아래 문서 규칙 준수)
2. `index.html` 의 `DOCS` 배열 **맨 위**에 매니페스트 1줄 추가
3. `git add -A && git commit -m "docs: <제목>" && git push`
4. 커밋 완료 후 Pages URL 경로를 사용자에게 알려줄 것

## 문서 규칙

- **단일 파일**: CSS/JS 전부 인라인. 외부 의존은 Paperlogy 폰트 CDN만 허용
  `https://cdn.jsdelivr.net/gh/fonts-archive/Paperlogy/subsets/Paperlogy-dynamic-subset.css`
- **템플릿**: `docs/example-consistent-hashing.html` 을 복제해서 시작 (탭/복사버튼 JS 포함)
- **필수 구조**:
  - `<a href="../index.html">← HTML Docs</a>` 브레드크럼
  - eyebrow(카테고리·날짜) + 제목 + 리드 + TL;DR 박스(3줄 이내)
  - 긴 세부는 `<details>`, 변형(언어/환경별)은 탭, 재사용 코드에는 복사 버튼
  - 비교는 테이블 또는 나란히 배치, 구조/흐름은 인라인 SVG 다이어그램
- **접근성**: focus-visible 아웃라인, prefers-reduced-motion 대응 유지

## 디자인 토큰 (모든 문서 공통 — 변경 금지)

```css
--bg:#0A1428; --panel:#101D38; --panel2:#152547;
--line:#233a66; --ink:#E8EEF9; --dim:#8DA2C6; --faint:#5A6E93;
--accent:#F5B841; --accent-ink:#241a04;
--ok:#4ADE80; --warn:#FB7185;
```

폰트: Paperlogy / 코드: ui-monospace, Consolas, D2Coding

## 매니페스트 형식 (index.html 내 DOCS 배열)

```js
{ file: "docs/20260715-hermes-setup.html",
  title: "Hermes Agent 설정 정리",
  desc: "한 문장 요약 (검색 대상이 되므로 핵심 키워드 포함)",
  cat: "인프라",   // 자유 — 필터에 자동 반영. 기존 카테고리 우선 재사용
  date: "2026-07-15" },
```

## 금지 사항

- index.html 의 스크립트 로직·스타일을 문서 추가 목적으로 수정하지 말 것 (매니페스트만)
- 문서에 외부 JS 라이브러리 CDN 추가 금지 (self-contained 원칙)
- 기존 문서를 요청 없이 수정/삭제하지 말 것
- force push 금지

## 취합 요청 처리

"문서 A와 B를 합쳐줘" 요청 시: 새 통합 문서를 생성하고, 기존 문서는 삭제하되
매니페스트에서 두 항목을 제거하고 통합 문서 1줄로 교체. 커밋 메시지: `docs: merge <A>+<B>`
