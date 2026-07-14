# 표준 요청 프롬프트 (Claude에 붙여넣기)

---

아래 주제를 **자기완결형 단일 HTML 파일**로 정리해줘. 규칙:

1. **단일 파일**: CSS/JS 전부 인라인. 외부 의존은 폰트 CDN(Paperlogy jsDelivr)만 허용.
2. **디자인 토큰** (내 문서 허브와 통일):
   - 배경 `#0A1428`, 패널 `#101D38`, 선 `#233a66`
   - 본문 `#E8EEF9`, 보조 `#8DA2C6`, 액센트 `#F5B841`
   - 폰트: Paperlogy (https://cdn.jsdelivr.net/gh/fonts-archive/Paperlogy/subsets/Paperlogy-dynamic-subset.css)
3. **필수 구조**:
   - 상단: 카테고리 eyebrow + 제목 + 1~2문장 리드 + **TL;DR 박스(3줄 이내)**
   - 상단에 `<a href="../index.html">← HTML Docs</a>` 브레드크럼
   - 긴 세부 내용은 `<details>` 접힘, 같은 내용의 변형(언어/환경별)은 탭
   - 재사용할 코드/설정에는 복사 버튼
   - 비교가 있으면 테이블 또는 나란히 배치
4. **내용 형식은 주제에 맞게 선택**: 비교 문서 / 설명서(explainer) / 계획서 / 다이어그램(인라인 SVG) / 리포트 / 인터랙티브 데모
5. **한국어**, 간결하게. 파일명은 `YYYYMMDD-주제.html` 형식으로 제안해줘.
6. 마지막에 index.html의 DOCS 배열에 추가할 **매니페스트 1줄**도 함께 출력해줘.

정리할 주제:
(여기에 주제/자료 붙여넣기)
