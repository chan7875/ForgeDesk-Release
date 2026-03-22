<p align="center">
  <img src="logo.png" width="128" alt="ForgeDesk — Desktop GUI for Claude Code" />
</p>

<h1 align="center">ForgeDesk</h1>
<h3 align="center">Desktop GUI for Claude Code</h3>

<p align="center">
  <strong>Claude Code & Codex를 위한 네이티브 데스크탑 앱.</strong><br/>
  멀티 스레드, 파일 첨부, ForgeBrowser, 리뷰 워크플로우, Git 통합까지 — 하나의 앱에서.<br/>
  <em>SvelteKit + Tauri 2 + Rust로 만든 개발자용 AI 코딩 데스크탑.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-0.2.0-blue" alt="Version" />
  <img src="https://img.shields.io/badge/platform-macOS%20(Apple%20Silicon)-black?logo=apple" alt="macOS Apple Silicon" />
  <img src="https://img.shields.io/badge/platform-macOS%20(Intel)-gray?logo=apple" alt="macOS Intel" />
  <img src="https://img.shields.io/badge/Built%20with-Rust-orange?logo=rust" alt="Rust" />
  <img src="https://img.shields.io/badge/Framework-Tauri%202-blue?logo=tauri" alt="Tauri 2" />
  <img src="https://img.shields.io/badge/Frontend-SvelteKit%205-ff3e00?logo=svelte" alt="SvelteKit" />
</p>

---

## ForgeDesk란?

**ForgeDesk**는 [Claude Code](https://github.com/anthropics/claude-code)를 위한 네이티브 데스크탑 GUI입니다.

Claude Code와 Codex CLI를 브라우저 없이 전용 데스크탑 앱에서 실행하세요. 대화 스레드를 로컬에 영속 저장하고, 도구 호출 결과를 시각적으로 확인하며, URL 한 번으로 웹 페이지 컨텍스트를 Claude에게 전달합니다. Git 리뷰 워크플로우, 멀티탭 내장 터미널, Telegram 원격 연동까지 — 개발 흐름을 끊지 않는 올인원 AI 코딩 환경입니다.

---

## 주요 기능

### AI 채팅 & 세션 관리

| 기능 | 설명 |
| --- | --- |
| Claude / Codex 전환 | 입력창에서 CLI 프로바이더를 즉시 전환 |
| 스레드 히스토리 | `~/.claude/` 로컬 세션 데이터 기반 대화 이력 유지 |
| 멀티 스레드 탭 | 세션 탭과 사이드바로 여러 대화 동시 관리 |
| Plan Mode | Claude Plan Mode 결과를 `plan.md`에 저장하고 승인 플로우 제공 |
| Handoff | `plan.md` / `memory.md` / `handoff.md` 기반 프로바이더 간 컨텍스트 전달 |
| 최근 워크스페이스 | 헤더에서 최근 프로젝트 목록 확인 및 원클릭 전환 |
| 데스크탑 알림 | 작업 완료 시 시스템 알림 |

### 파일 첨부

| 기능 | 설명 |
| --- | --- |
| 이미지 | `png`, `jpg`, `jpeg`, `gif`, `webp` (최대 20 MB, 10개) |
| 문서 | `pdf`, `txt` |
| `@` 멘션 | 워크스페이스 파일/폴더 자동완성 |

### ForgeBrowser

| 기능 | 설명 |
| --- | --- |
| URL 컨텍스트 캡처 | 채팅 입력창에 URL 붙여넣기 → 스크린샷 + 페이지 텍스트 + 인터랙티브 요소 자동 첨부 |
| CDP 연결 | 포트 9222에서 실행 중인 Chrome에 CDP로 연결, 없으면 헤드리스 Chromium 폴백 |
| Playwright 자동 설치 | 최초 사용 시 Chromium 브라우저 설치 안내 (~100 MB, 1회) |
| 자동화 스크립트 | `threads-auto-like.mjs`, `threads-post-scraper.mjs` 내장 |

### Review Mode

| 기능 | 설명 |
| --- | --- |
| 리뷰 소스 | 로컬 변경사항 / staged / 브랜치 diff / GitHub PR URL |
| 실시간 진행 표시 | 현재 단계 텍스트 + findings 수 실시간 업데이트 |
| 구조화된 결과 | severity / category 메타데이터 포함 findings |
| GitHub 리뷰 제출 | `gh` CLI를 통한 PR 리뷰 게시 |
| 리뷰 히스토리 | 프리셋 및 최근 리뷰 이력 관리 |

### Git 통합

| 기능 | 설명 |
| --- | --- |
| Working Tree 상태 | 변경 파일 목록 및 상태 표시 |
| Diff 뷰어 | 파일별 변경 내용 인라인 표시 |
| 브랜치 비교 | 브랜치 간 diff 및 커밋 로그 |
| Staging | 파일 스테이징 / 언스테이징 |
| 커밋 & PR | 커밋 메시지 생성, PR 설명 생성, `gh`를 통한 PR 생성 |

### 내장 터미널

| 기능 | 설명 |
| --- | --- |
| 멀티탭 | 프로젝트별 여러 터미널 탭 생성, 이름 변경, 복제 |
| 분할 화면 | 좌우/상하 분할, divider 드래그로 비율 조절 |
| 상태 복원 | 마지막 작업 디렉터리, 분할 레이아웃, 비율 자동 저장·복원 |
| 빠른 실행 | 프로젝트 chip 클릭으로 해당 프로젝트 터미널 즉시 오픈 |

### Telegram 연동

| 기능 | 설명 |
| --- | --- |
| 응답 전송 | 활성 세션의 Claude / Codex 응답을 Telegram으로 자동 전송 |
| 메시지 수신 | Telegram 메시지를 앱 세션으로 가져와 CLI 실행 |
| 슬래시 명령 | `/status`, `/usage`, `/changecli` 앱 내·Telegram 공통 지원 |

### 설정 영속화

| 기능 | 설명 |
| --- | --- |
| 파일 시스템 저장 | 설정을 `~/.config/forgedesk/config.json`에 저장 — 재설치 후에도 유지 |
| 자동 마이그레이션 | 기존 localStorage 데이터를 최초 1회 파일 시스템으로 자동 마이그레이션 |
| 워크스페이스 제거 | 최근 프로젝트 목록에서 X 버튼으로 항목 삭제 |

---

## 화면 구성

```
+------------------------------------------------+
| [워크스페이스▼]  [최근 프로젝트...]  [Settings] |  ← 헤더
+--------------------+---------------------------+
|                    |  채팅 스레드              |
|  사이드바          |  Tool 호출 결과 표시      |
|  (스레드 목록,     |  파일 첨부 / @ 멘션       |
|   Git, Review)     |  ForgeBrowser 캡처 결과   |
|                    +---------------------------+
|                    |  입력창                   |
|                    |  [URL / 텍스트 / 파일]    |
+--------------------+---------------------------+
|  내장 터미널 (Cmd+J)                           |
|  [탭1] [탭2] [New] [Duplicate] [Split]         |
+------------------------------------------------+
```

---

## 설치 및 실행

현재 ForgeDesk는 로컬 빌드를 통해 사용하는 것을 권장합니다.

### 사전 요구사항

**필수**

- Node.js 20+
- npm 10+
- Rust 툴체인
- Tauri 플랫폼 빌드 요구사항 ([Tauri 공식 가이드](https://tauri.app/start/prerequisites/) 참고)
- Claude Code 또는 Codex CLI

**선택**

- GitHub CLI (`gh`) — PR 목록 조회, PR 생성, PR 리뷰 제출
- Telegram 봇 토큰 + Chat ID — Telegram 연동
- Playwright Chromium (~100 MB) — ForgeBrowser URL 캡처 (앱 내 설치 지원)
- Chrome with `--remote-debugging-port=9222` — CDP 기반 캡처

### 의존성 설치

```bash
npm install
```

### 개발 모드 실행

```bash
npm run tauri dev
```

### 프로덕션 빌드

```bash
npm run tauri build
```

---

## 빠른 시작

1. **워크스페이스 선택** — 앱 시작 후 온보딩 화면에서 프로젝트 폴더를 선택합니다.
2. **채팅 시작** — Claude Code 또는 Codex CLI를 선택하고 채팅을 시작합니다.
3. **파일 첨부** — `@` 멘션으로 워크스페이스 파일을 첨부하거나 이미지/PDF를 드래그합니다.
4. **URL 캡처** — 채팅 입력창에 URL을 붙여넣으면 ForgeBrowser가 페이지를 캡처해 Claude에게 전달합니다.
5. **Git 리뷰** — 사이드바에서 Review 패널을 열고 리뷰 소스를 선택해 코드 리뷰를 실행합니다.
6. **터미널** — `Cmd+J`로 내장 터미널을 열고 멀티탭·분할 화면을 활용합니다.
7. **Telegram 연동** — 설정 > Telegram 탭에서 봇 토큰을 입력해 원격 세션 제어를 설정합니다.

---

## ForgeBrowser 상세

### URL 컨텍스트 캡처

1. 채팅 입력창에 URL을 붙여넣습니다.
2. 링크 미리보기 또는 캡처 버튼이 나타나면 캡처를 실행합니다.
3. **스크린샷**이 첨부파일로, **페이지 텍스트**와 **인터랙티브 요소 목록**이 프롬프트 앞에 자동으로 추가됩니다.

### 기존 Chrome에 CDP로 연결 (선택)

```bash
# macOS
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --remote-debugging-port=9222
```

포트 9222로 Chrome을 실행하면 ForgeBrowser가 헤드리스 모드 대신 실행 중인 브라우저 세션에 접속합니다.

### Playwright 브라우저 설치

처음 URL 캡처 시도 시 설치 안내가 자동으로 표시됩니다. 설정 화면에서 수동으로 설치할 수도 있습니다.

---

## Review Mode 상세

### 리뷰 실행

1. Review 런처 열기 (Git 패널 또는 단축키)
2. 리뷰 소스 선택 (로컬 변경, staged, 브랜치 diff, PR URL)
3. **Start Review** 클릭
4. 런처 하단에서 실시간 진행 상황 확인:
   ```
   ⠋  Analyzing 5 files...
      3 findings so far
   ```
5. 리뷰 완료 후 런처가 닫히고 결과 패널이 열립니다.

---

## Telegram 연동 상세

### 초기 설정

1. 설정 > **Telegram** 탭을 엽니다.
2. BotFather에서 발급받은 **봇 토큰**을 입력합니다.
3. `Detect Chat ID` 또는 수동 입력으로 **채팅 ID**를 설정합니다.
4. `Enable Telegram`, `Send App Responses`, `Receive Telegram Messages`를 원하는 대로 활성화합니다.
5. `Test Connection`으로 연결을 확인합니다.

### 슬래시 명령

| 명령 | 설명 |
| --- | --- |
| `/status` | 현재 세션 상태 확인 |
| `/usage` | Claude 사용량 조회 |
| `/changecli` | 활성 CLI 프로바이더 전환 |

---

## Provider Handoff

Claude와 Codex 사이를 전환할 때 컨텍스트를 유지합니다.

- **handoff 버튼** 클릭 → 반대 provider용 handoff 프롬프트를 자동으로 작성하고 입력창에 채웁니다.
- 워크스페이스 루트의 `plan.md`, `memory.md`, `handoff.md`가 공통 컨텍스트로 사용됩니다.
- Claude Plan Mode 결과는 `plan.md`에 자동 저장됩니다.

---

## 설정 저장 경로

```
~/.config/forgedesk/config.json
```

앱 번들과 독립적으로 홈 디렉터리에 저장되므로 재설치·재빌드 후에도 설정과 스레드 히스토리가 유지됩니다.

---

## 기술 스택

| 영역 | 기술 |
| --- | --- |
| Frontend | SvelteKit, Svelte 5, TypeScript |
| Desktop Shell | Tauri 2 |
| Backend | Rust |
| Terminal | xterm.js |
| Browser Automation | Playwright (Chromium) |

---

## 추가 문서

- [Chat, Workspace, Telegram 업데이트](doc/chat-workspace-telegram.md)
- [Terminal Workspace 업데이트](doc/terminal-workspaces.md)
- [설정 영속화 및 워크스페이스 제거](doc/persistent-config.md)
- [ForgeBrowser URL 캡처](doc/forgebrowser-url-capture.md)
- [Review Progress Indicator](doc/review-progress-indicator.md)

---

## 노트

- ForgeDesk는 `~/.claude/` 하위 Claude 로컬 세션 데이터에서 스레드 히스토리를 읽습니다.
- macOS에서 앱을 셸 밖에서 실행할 때 사용 가능한 `node` 바이너리를 찾는 추가 로직이 포함되어 있습니다.
- 내장 터미널은 선택한 워크스페이스 기준으로 `/bin/zsh`를 실행합니다.
- 터미널 탭의 현재 작업 디렉터리, 분할 방향, 비율은 로컬 저장소에 유지됩니다.
