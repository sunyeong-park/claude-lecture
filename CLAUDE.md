# 클로드 기초 강의 교안 — 프로젝트 규칙

## 프로젝트 개요
- **파일명**: claude_lecture.html
- **형식**: 단일 HTML 파일 (CSS·JS 전부 포함)
- **대상**: 개발 사전지식 없는 일반 직장인
- **환경**: Windows 전용 / Claude Pro 플랜 기준
- **총 강수**: 8강 (8강은 2차수 예정)

---

## 기본 규칙

- 모든 답변은 한국어로
- 파일 삭제는 절대 하지 말 것 (수정만 허용)
- 수정 전 반드시 현재 파일 구조 파악할 것
- 작업 완료 후 반드시 outputs 폴더에 저장할 것

---

## HTML 파일 구조

### 레이아웃 (고정 — 절대 변경 금지)
```
body { padding-left: 220px; padding-top: 58px; }
.sidebar { position: fixed; top: 0; left: 0; bottom: 0; width: 220px; }
.site-header { position: fixed; top: 0; left: 220px; right: 0; height: 58px; }
```
- 사이드바와 헤더는 `position:fixed` 방식 고정
- body에 `padding-left:220px; padding-top:58px` 로 본문 밀어내기
- **이 레이아웃을 변경하면 화면이 깨짐 — 절대 건드리지 말 것**

### 색상 테마 (강별)
| 강 | 색상 변수 | 비고 |
|---|---|---|
| 1강 | `--blue-400` (#378ADD) | |
| 2강 | `--coral-400` (#D85A30) | |
| 3강 | `--purple-400` (#7F77DD) | |
| 4강 | `--teal-400` (#1D9E75) | |
| 5강 | `--amber-400` (#BA7517) | |
| 6강 | `--green-400` (#639922) | |
| 7강 | `--gray-600` (#5F5E5A) | |
| 8강 | 배경 #fffbeb + 번호 #ef4444 | 2차수 예정 |

---

## 컴포넌트 클래스 목록

| 클래스 | 용도 | 색상 |
|---|---|---|
| `.concept-box` | 개념 설명 박스 | 파란색 |
| `.purple-box` | 개념 설명 박스 | 보라색 |
| `.practice` | 실습 체크 박스 | 청록색 |
| `.tip` | 팁·주의사항 | 노란색 |
| `.error-section` | 오류 해결 | 빨간색 |
| `.code-block` | 코드 블록 (복사 버튼 포함) | 다크 |
| `.steps` | 번호 스텝 리스트 | 파란 번호 |
| `.two-col` | 2열 카드 그리드 | |
| `.three-col` | 3열 카드 그리드 | |
| `.mini-card` | 기본 카드 | 회색 |
| `.mini-card.teal` | 데이터·인프라 용어 카드 | 청록 |
| `.mini-card.purple` | 도로·API 용어 카드 | 보라 |

### 코드 블록 문법 강조
| 클래스 | 용도 | 색상 |
|---|---|---|
| `.cm` | 주석 | 초록 #6a9955 |
| `.cmd` | 명령어 | 파랑 #569cd6 |
| `.str` | 문자열 | 주황 #ce9178 |
| `.kw` | 키워드 | 보라 #c586c0 |
| `.ok` | 성공·결과 | 청록 #4ec9b0 |

---

## 커리큘럼 구조

### 1강 — 클로드 개념 이해 & Pro 플랜 설치
- AI·LLM·에이전트 개념, Pro 가입, Desktop 설치, 첫 프롬프트

### 2강 — 사용량 확인 · 기초 개발 용어 · CLI 입문
- Billing & Usage 확인
- AI 용어 5개: 토큰, 모델, 패키지/npm, CLI, 경로
- 인프라 용어 7개 (도로 비유): DB(창고), 클라우드(남의 데이터센터), 서버(도로), API(전용도로+규칙), RLS(경비원), SQL(DB에 말 거는 언어), 인덱스(속도 최적화)
- PowerShell 기본 명령어

### 3강 — Node.js CLI 설치 & Claude Code 실행
- winget으로 Node.js 설치
- npm 없을 때 CLI 직접 설치 3가지 방법 (STEP 1-3)
- Claude Code 설치 및 경로 확인
- `--dangerously-skip-permissions` 옵션
- 기본 슬래시 명령어 (/help, /clear, /compact, /status)

### 4강 — GitHub 개념 & CLI · CLAUDE.md 활용
- **순서**: STEP1=GitHub 계정·저장소 → STEP2=Git 설치 → STEP3=Claude Code로 push → STEP3-1=Pages 배포 → STEP4=CLAUDE.md
- Git 설치: `winget install Git.Git`
- Claude Code로 "GitHub에 올려줘" 한 마디로 add·commit·push 자동
- GitHub Pages: 브라우저에서 최초 1회 활성화 → 이후 push하면 자동 배포
- CLAUDE.md: Claude Code가 폴더에서 실행 시 자동으로 읽는 지시 파일

### 5강 — MCP · Skills 개념 & 서브 에이전트 · Teams
- MCP 개념 (비유: 두뇌에 손발 달기)
- Skills 개념 (비유: 요리사 레시피 카드)
- 서브 에이전트: 팀장(취합·검수·재오더) + 리서처 + 라이터 3개 구성
- 서브 에이전트(탑다운) vs Teams(바텀업/커뮤니케이션) 비교
- STEP 순서: 에이전트 3개 생성 → 폴더 확인 → Teams 등록 → 커피챗 → 멈추기 → 파이프라인

### 6강 — Notion MCP 연결 실습
- Notion API 토큰 발급 (notion.so/my-integrations)
- Claude CLI에서 환경변수로 직접 연결:
  ```
  $env:NOTION_TOKEN = "secret_토큰"
  claude
  ```
- .env 파일로 저장해두면 다음부터는 claude만 실행하면 됨
- **Desktop config.json 방식 사용 안 함 — CLI 환경변수 방식만 사용**

### 7강 — Discord 봇 만들기 & Notion 자동 메모 저장
- 6강 Notion 토큰 그대로 재사용
- STEP1: Discord 봇 생성 & 토큰 발급
- STEP1-1: discord.js 플러그인 설치 + .env 파일에 두 토큰 페어링
- STEP2: Claude Code에게 bot.js 코드 요청 (직접 코딩 없이)
- STEP3: 패키지 설치 & 봇 실행
- STEP4: Discord에서 `!메모` 입력 → Notion 자동 저장 테스트

### 8강 — 부서별 업무 자동화 (2차수 예정)
- 노란 배경(#fffbeb) + 빨간 번호(#ef4444) + 점선 테두리
- 클릭 비활성화 (`.coming` 클래스)

---

## 사이드바 네비게이션

- 8개 강의 목록 고정 표시
- 클릭 시 smooth scroll로 해당 강의 이동
- 스크롤하면 현재 강의 자동 하이라이트 (`.active` 클래스)
- 8강은 클릭 비활성화

---

## 파일 수정 시 주의사항

1. **레이아웃 CSS 절대 건드리지 말 것** (body padding, sidebar fixed, header fixed)
2. 강의 내용 추가·수정 시 해당 `id="lecN"` 블록만 수정
3. 새 강의 추가 시 사이드바 nav-item도 함께 추가
4. 코드 블록의 복사 버튼은 `onclick="copyCode(this)"` 유지
5. 8강 스타일 (노란 배경) 건드리지 말 것

---

## 다음 대화에서 이어서 작업하는 방법

```
claude_lecture.html 파일을 열어서 확인해줘.
아래 내용을 수정해줘:
[수정할 내용 입력]
```

수정 완료 후 반드시:
```bash
cp claude_lecture.html /mnt/user-data/outputs/claude_lecture.html
```
