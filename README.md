# HTML Docs

주제별 정리를 **자기완결형 단일 .html 파일**로 축적하는 개인 문서 허브.
참고: [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/)

## 구조

```
/
├── index.html          # 취합 허브 (문서 카드 목록 + 검색 + 카테고리 필터)
├── docs/               # 문서 본체 (파일 1개 = 문서 1개)
│   └── example-consistent-hashing.html   # 복제용 템플릿
├── PROMPT.md           # Claude에게 문서 생성을 요청할 때 붙여넣는 표준 프롬프트
└── README.md
```

## 최초 설정 (1회)

1. GitHub에 새 저장소 생성 (예: `html-docs`)
2. 이 폴더 전체를 push
3. 저장소 **Settings → Pages → Source: `main` branch / root** 선택
4. `https://<아이디>.github.io/html-docs/` 로 접속 확인

## 새 문서 추가 워크플로

1. Claude에 `PROMPT.md` 내용 + 정리할 주제/자료를 붙여넣어 .html 파일을 받는다
2. 받은 파일을 `docs/` 에 저장 (파일명: `YYYYMMDD-주제.html` 권장)
3. `index.html` 의 `DOCS` 배열 맨 위에 항목 1줄 추가:

```js
{ file: "docs/20260715-hermes-setup.html",
  title: "Hermes Agent 설정 정리",
  desc: "Docker 재시작 시퀀스, config.yaml 구조, /reset 절차",
  cat: "인프라", date: "2026-07-15" },
```

4. commit & push → 1분 내 Pages에 반영

## 규칙

- **문서 1개 = 파일 1개**, 외부 JS/CSS 의존 없음 (폰트 CDN 제외)
- 문서 상단에 반드시 TL;DR 박스
- 재사용할 코드/설정에는 복사 버튼
- 카테고리는 자유 — index의 필터 칩에 자동 반영됨

## 편집/취합

- 편집: 파일이 곧 소스이므로 직접 수정 후 push, 또는 파일을 Claude에 업로드해서 수정 요청
- 취합: 여러 문서를 Claude에 업로드하고 "하나의 문서로 통합" 요청 → 새 .html로 교체
