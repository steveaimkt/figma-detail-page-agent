# 피그마 에이전트 빠른 시작 가이드

GitHub에서 다운로드 → Antigravity에서 Claude Code 실행 → Figma 작업까지의 전체 과정입니다.

---

## 전체 흐름

```
1. GitHub에서 다운로드
       ↓
2. Antigravity + Figma 설치
       ↓
3. Antigravity에서 프로젝트 열기
       ↓
4. Claude Code로 상세페이지 JSON 생성
       ↓
5. Figma 플러그인으로 레이아웃 생성
       ↓
6. Figma에서 이미지 교체 및 편집
```

---

## Step 1: GitHub에서 다운로드

1. https://github.com/steveaimkt/figma-detail-page-agent 접속
2. 초록색 **Code** 버튼 클릭
3. **Download ZIP** 선택
4. 다운로드된 ZIP 파일 압축 해제

---

## Step 2: 프로그램 설치

### 2.1 Antigravity 설치

1. https://antigravity.so/ 접속
2. **Download** 버튼 클릭
3. 설치 후 실행

> Antigravity에는 Claude Code가 기본 내장되어 있습니다.

### 2.2 Figma Desktop 설치

1. https://www.figma.com/downloads/ 접속
2. Desktop App 다운로드
3. 설치 후 Figma 계정으로 로그인

---

## Step 3: 프로젝트 설정

### 3.1 Antigravity에서 프로젝트 열기

1. Antigravity 실행
2. **File** → **Open Folder...**
3. 다운받은 `figma-detail-page-agent` 폴더 선택
4. **Open** 클릭

### 3.2 Figma 플러그인 설치

1. **Figma Desktop** 실행
2. 아무 파일이나 열기 (또는 새 파일 생성)
3. 상단 메뉴: **Plugins** → **Development** → **Import plugin from manifest...**
4. 다운받은 폴더에서 `figma-plugin/manifest.json` 파일 선택
5. **열기** 클릭

**확인**: **Plugins** → **Development** 메뉴에 **Detail Page Layout Generator**가 보이면 성공

---

## Step 4: Claude Code로 상세페이지 JSON 생성

### 4.1 Claude Code 실행

Antigravity 하단의 채팅창을 사용합니다.

### 4.2 상세페이지 생성 요청

Claude Code에게 다음 형식으로 요청:

```
다음 제품의 상세페이지 레이아웃 JSON을 생성해주세요.

제품명: [제품명]
브랜드: [브랜드명]
카테고리: [카테고리]

핵심 기능 6가지:
1. [기능명]: [설명]
2. [기능명]: [설명]
3. [기능명]: [설명]
4. [기능명]: [설명]
5. [기능명]: [설명]
6. [기능명]: [설명]

타겟 고객: [누구에게 적합한지]
핵심 차별점: [경쟁사와 다른 점]
가격: [가격]

크래프트볼트/craftvolt-chainsaw-v3-final.json을 참고하여
24섹션 구조의 JSON 파일을 output/[제품명].json으로 저장해주세요.
```

### 4.3 예시 요청

```
다음 제품의 상세페이지 레이아웃 JSON을 생성해주세요.

제품명: 스마트 공기청정기 A1
브랜드: 클린에어
카테고리: 가전/공기청정기

핵심 기능 6가지:
1. 4단계 필터 시스템: 초미세먼지 99.9% 제거
2. 스마트 자동 모드: 공기질 감지하여 자동 풍량 조절
3. 저소음 설계: 수면 모드 20dB 이하
4. 넓은 커버리지: 60평형까지 사용 가능
5. 필터 교체 알림: 앱으로 필터 상태 실시간 확인
6. 에너지 절약: 24시간 사용해도 월 3,000원

타겟 고객: 영유아 가정, 반려동물 가정, 미세먼지 민감 가정
핵심 차별점: 업계 최대 커버리지 + 최저 소음
가격: 599,000원

크래프트볼트/craftvolt-chainsaw-v3-final.json을 참고하여
24섹션 구조의 JSON 파일을 output/cleanair-a1.json으로 저장해주세요.
브랜드 컬러는 #00A8E8 (파란색)으로 설정해주세요.
```

### 4.4 생성 완료 확인

Claude Code가 작업을 완료하면:
- `output/` 폴더에 JSON 파일이 생성됨
- 파일을 열어 내용 확인

### 4.5 수정 요청 (필요시)

```
방금 생성한 JSON에서 다음을 수정해줘:
- FAQ 질문을 7개로 늘려줘
- 후기 섹션에 후기 2개 더 추가해줘
```

---

## Step 5: Figma 플러그인으로 레이아웃 생성

### 5.1 JSON 파일 복사

1. Antigravity에서 생성된 JSON 파일 열기 (`output/[제품명].json`)
2. 전체 선택: `Cmd+A` (Mac) / `Ctrl+A` (Windows)
3. 복사: `Cmd+C` (Mac) / `Ctrl+C` (Windows)

### 5.2 Figma에서 플러그인 실행

1. **Figma Desktop** 실행
2. 새 파일 생성 (또는 기존 파일 열기)
3. 메뉴: **Plugins** → **Development** → **Detail Page Layout Generator**

### 5.3 레이아웃 생성

1. 플러그인 창의 텍스트 영역에 복사한 JSON 붙여넣기
2. **생성** 버튼 클릭
3. "레이아웃이 성공적으로 생성되었습니다!" 메시지 확인

---

## Step 6: Figma에서 편집

### 6.1 텍스트 수정

1. 수정할 텍스트 더블클릭
2. 내용 수정
3. 바깥 영역 클릭하여 완료

### 6.2 이미지 교체

1. **IMAGE_AREA** 프레임 선택 (회색 영역)
2. 우측 패널에서 **Fill** 섹션 찾기
3. 색상 박스 클릭 → **Image** 탭 선택
4. **Choose Image** 클릭
5. 원하는 이미지 파일 선택

### 6.3 색상 변경

1. 변경할 요소 선택
2. 우측 패널에서 **Fill** 색상 클릭
3. 새 색상 입력

---

## 완성 후 내보내기

### 이미지로 내보내기

1. 전체 프레임 선택
2. 우측 패널 하단 **Export** 섹션
3. **+** 버튼 → 형식 선택 (PNG 권장)
4. **Export** 버튼 클릭

---

## 문제 해결

| 문제 | 해결 방법 |
|------|----------|
| Claude Code가 응답 안 함 | 인터넷 연결 확인, Antigravity 재시작 |
| Figma 플러그인이 안 보임 | Figma 재시작, 플러그인 다시 가져오기 |
| JSON 붙여넣기 오류 | JSON 전체가 복사되었는지 확인 |

---

## 요약: 전체 과정 체크리스트

```
□ GitHub에서 ZIP 다운로드 및 압축 해제
□ Antigravity 설치
□ Figma Desktop 설치
□ Antigravity에서 프로젝트 폴더 열기
□ Figma 플러그인 설치 (manifest.json)
□ Claude Code로 JSON 생성
□ Figma에서 레이아웃 생성
□ 이미지 교체 및 편집
□ 내보내기
```

---

## 파일 위치

| 용도 | 경로 |
|------|------|
| 기준 템플릿 | `크래프트볼트/craftvolt-chainsaw-v3-final.json` |
| 생성된 파일 | `output/[제품명].json` |
| Figma 플러그인 | `figma-plugin/manifest.json` |

---

*이 가이드를 따라 하시면 AI로 상세페이지를 빠르게 제작할 수 있습니다!*
