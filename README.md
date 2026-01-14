# 피그마 상세페이지 에이전트

AI 기반 상세페이지 자동 제작 시스템입니다.
제품 정보만 입력하면 24섹션 구조의 상세페이지 레이아웃을 자동으로 생성합니다.

---

## 필요한 프로그램

| 프로그램 | 다운로드 |
|---------|----------|
| **Antigravity** | https://antigravity.so/ |
| **Figma Desktop** | https://www.figma.com/downloads/ |

> Antigravity에는 Claude Code가 기본 내장되어 있습니다.

---

## 빠른 시작

### 1. 프로젝트 다운로드

1. 이 저장소에서 **Code** → **Download ZIP** 클릭
2. 압축 해제

### 2. Antigravity에서 프로젝트 열기

1. Antigravity 실행
2. **File** → **Open Folder...**
3. 다운받은 폴더 선택

### 3. Figma 플러그인 설치

1. Figma Desktop 실행
2. **Plugins** → **Development** → **Import plugin from manifest...**
3. `figma-plugin/manifest.json` 파일 선택

### 4. 상세페이지 생성

Antigravity의 Claude Code에게 요청:

```
다음 제품의 상세페이지 레이아웃 JSON을 생성해주세요.

제품명: [제품명]
브랜드: [브랜드명]

핵심 기능 6가지:
1. [기능명]: [설명]
2. [기능명]: [설명]
3. [기능명]: [설명]
4. [기능명]: [설명]
5. [기능명]: [설명]
6. [기능명]: [설명]

타겟 고객: [타겟]
핵심 차별점: [차별점]
가격: [가격]

크래프트볼트/craftvolt-chainsaw-v3-final.json을 참고하여
24섹션 구조의 JSON 파일을 output/[제품명].json으로 저장해주세요.
```

### 5. Figma에 적용

1. 생성된 JSON 파일 전체 복사 (`Cmd+A` → `Cmd+C`)
2. Figma에서 **Plugins** → **Development** → **Detail Page Layout Generator**
3. JSON 붙여넣기 → **생성** 클릭

### 6. 편집 및 완성

- **텍스트 수정**: 더블클릭하여 수정
- **이미지 교체**: IMAGE_AREA 선택 → Fill → Image → Choose Image
- **내보내기**: Export → PNG

---

## 폴더 구조

```
figma-detail-page-agent/
├── 크래프트볼트/                  # 기준 템플릿 (예제)
│   └── craftvolt-chainsaw-v3-final.json
├── figma-plugin/                 # Figma 플러그인
│   ├── manifest.json
│   ├── code.js
│   └── ui.html
├── templates/                    # 섹션 구조 템플릿
└── output/                       # 생성된 파일 저장
```

---

## 24섹션 구조

| 순서 | 섹션 | 목적 |
|------|------|------|
| 01 | Hook | 메인 카피로 시선 사로잡기 |
| 02 | WhatIsThis | 제품 한마디 정의 |
| 03 | BrandName | 브랜드 의미 |
| 04 | SetContents | 구성품 안내 |
| 05 | WhyCore | 핵심 기능 중요성 |
| 06 | PainPoint | 고객 불편함 공감 |
| 07 | Solution | 해결책 제시 |
| 08 | FeaturesOverview | 6가지 핵심 기능 개요 |
| 09-14 | Feature1~6_Detail | 각 기능 상세 설명 |
| 15 | Tips | 사용 꿀팁 |
| 16 | Differentiator | 핵심 차별화 |
| 17 | Comparison | 경쟁사 비교 |
| 18 | Safety | 안전/신뢰 |
| 19 | Target | 추천 대상 |
| 20 | Reviews | 고객 후기 |
| 21 | ProductSpec | 제품 스펙 |
| 22 | FAQ | 자주 묻는 질문 |
| 23 | Warranty | 보증/정책 |
| 24 | CTA | 구매 유도 |

---

## 상세 가이드

자세한 사용법은 [QUICKSTART-GUIDE.md](QUICKSTART-GUIDE.md)를 참고하세요.

---

## 문제 해결

| 문제 | 해결 방법 |
|------|----------|
| Figma 플러그인이 안 보임 | Figma 재시작 후 플러그인 다시 가져오기 |
| JSON 붙여넣기 오류 | JSON 전체가 복사되었는지 확인 |
| Claude Code 응답 없음 | 인터넷 연결 확인, Antigravity 재시작 |

---

## 라이선스

MIT License
