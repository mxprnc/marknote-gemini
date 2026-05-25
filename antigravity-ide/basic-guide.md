# Antigravity IDE 기초 가이드 (Basic Guide)

Google Antigravity IDE는 VS Code를 기반으로 구축된 강력한 **에이전트 중심(Agent-first) AI 개발 환경**입니다. 본 가이드는 Antigravity IDE를 사용할 때 필수적으로 알아야 할 기초 단축키, 주요 슬래시 명령어, 그리고 프로젝트 내 스킬 및 커맨드를 조회하는 방법에 대해 설명합니다.

---

## 1. 핵심 단축키 (Essential Keyboard Shortcuts)

Antigravity IDE는 AI 에이전트와 에디터를 유기적으로 연결하기 위해 다음과 같은 단축키를 제공합니다.

| 단축키 | 기능 이름 | 설명 |
| :--- | :--- | :--- |
| **`Cmd + K`** | 인라인 AI 편집 (Inline Edit) | 에디터에서 영역을 선택하거나 커서를 두고 호출하여, 자연어 요청을 통해 코드를 인라인으로 즉시 수정/생성합니다. |
| **`Cmd + L`** | AI 채팅 패널 토글 (AI Chat Panel) | 에디터 측면의 AI Chat 대화 창을 열거나 포커스하여 자유로운 질의응답 및 디버깅을 수행합니다. |
| **`Cmd + M`** | 에이전트 매니저 토글 (Agent Manager) | 백그라운드에서 실행 중인 여러 자율 에이전트들의 진행 상황을 모니터링하고 제어하는 '미션 컨트롤' 뷰를 엽니다. |
| **`Cmd + I`** | 인라인 명령어 (Inline Command) | 자연어를 입력하여 신속하게 코드를 생성하거나 리팩토링을 요청할 수 있는 또 다른 프롬프트 입력을 활성화합니다. |
| **`Shift + Tab`** | 모드 순환 전환 (Cycle Modes) | 구현(Execution) 모드, 계획(Plan) 모드 등을 순차적으로 전환합니다. |
| **`Ctrl + T`** | 계획 진행 상황 확인 (View Todos) | 현재 진행 중인 다단계 태스크(Todo List)의 진행 상황을 상시로 열어볼 수 있습니다. |

> [!TIP]
> **단축키 사용자 정의 방법**
> `Cmd + Shift + P`를 눌러 Command Palette를 연 후 **"Preferences: Open Keyboard Shortcuts"**를 선택하거나, `Cmd + ,` 설정을 통해 본인의 스타일에 맞게 단축키를 언제든지 변경할 수 있습니다.

---

## 2. 주요 슬래시 명령어 (Key Slash Commands)

에이전트와의 대화 창(Chat/CLI)에서 슬래시(`/`)를 입력하여 복잡한 자율 워크플로우나 기능을 바로 트리거할 수 있습니다.

### `/goal`
- **목적**: 장기 실행 태스크(Long-running Task) 실행
- **설명**: 에이전트에게 백그라운드에서 오랫동안 신중하게 수행해야 하는 최종 목표를 지정합니다. 이 명령을 사용하면 에이전트가 스스로 문제를 분석하고, 여러 차례의 검증 과정을 거쳐 목표가 완전히 달성될 때까지 멈추지 않고 작업을 수행합니다.
- **예시**: `/goal "프로젝트 내 모든 컴포넌트의 유닛 테스트를 작성하고 커버리지를 90% 이상으로 끌어올려줘"`

### `/grill-me`
- **목적**: 대화형 인터뷰 기반 설계 정렬 (Design Alignment)
- **설명**: 구현을 시작하기 전에 AI가 사용자에게 질문을 던지는 인터뷰 프로세스를 진행합니다. 이를 통해 아키텍처적 의사결정, 기술 스택, 예외 처리 설계 등의 모호한 요구사항을 명확히 정리하고 계획에 반영합니다.
- **예시**: `/grill-me "새로운 알림 시스템 구현을 위한 상세 설계 결정을 같이 진행해줘"`

### `/schedule`
- **목적**: 백그라운드 작업 예약 및 주기적 모니터링 (Timer & Cron)
- **설명**: 일회성 타이머(One-shot Timer) 또는 크론 표현식(Cron Expression)을 이용한 주기적인 알림 작업을 등록하여 백그라운드에서 진행 상황을 추적합니다.
- **예시**:
  - `/schedule 60s "빌드가 잘 끝났는지 다시 체크해줘"`
  - `/schedule "*/5 * * * *" "배포 상태 체크 후 알려줘"`

### `/browser` (또는 `@browser_agent`)
- **목적**: 웹 브라우저 자동화 실행 (Browser Automation)
- **설명**: 내장된 `browser_agent`를 활성화하여 에이전트가 웹 브라우저를 직접 띄우고(Headless/Persistent), 웹사이트를 탐색하거나 로그인 양식을 채우고, 스크린샷을 분석하며 데이터를 수집할 수 있도록 지원합니다.
- **예시**: `@browser_agent "https://example.com 에 접속해서 최신 배포 공지사항 본문을 긁어와줘"`

---

## 3. Skill 및 Command 확인 방법 (How to Check Skills & Commands)

현재 프로젝트와 에이전트에 등록된 모든 기능(Skill, Agent, Command)을 파악하는 방법은 다음과 같습니다. CLI 명령어 및 디렉터리 구조 확인 외에도 GUI 설정을 통해 편리하게 관리할 수 있습니다.

### ① GUI 설정을 통한 확인 (가장 직관적인 방법)
Antigravity IDE 내의 그래픽 사용자 인터페이스(GUI)를 통해 시각적으로 확인하고 제어할 수 있습니다.
- **접근 방법**: `Cmd + ,` (Windows/Linux는 `Ctrl + ,`) 단축키를 누르거나, 화면 좌측 하단의 톱니바퀴(Settings) 아이콘을 클릭하여 설정으로 진입합니다.
- **Customizations 메뉴**: Settings 화면에서 **Customizations** 메뉴를 클릭하면 다음과 같은 항목들을 조회하고 쉽게 켜고 끌 수 있습니다.
  - **MCP Servers**: 연동된 Model Context Protocol 서버들(예: BigQuery, Cloud Logging, GitHub 등)의 연결 상태 조회 및 관리
  - **Custom Skills & Plugins**: 설치된 커스텀 스킬 및 구글 플러그인 정보 확인
  - **Rules & Workflows**: 에이전트에 적용되는 규칙 및 커스텀 워크플로우 정의

### ② 에이전트 스킬(Agent Skills) 확인 (CLI 및 디렉터리)
에이전트 스킬은 특정 SOP(표준 업무 절차)를 정의한 마크다운 문서 패키지입니다.
- **대화형 세션 내부**: `/skills list` 또는 `/skills`를 입력하여 현재 발견된 스킬과 그 활성화 상태를 한눈에 볼 수 있습니다.
- **일반 터미널**: `agy skills list` 또는 `agy-ide skills list` 명령을 통해 전역/워크스페이스 스킬 목록을 확인합니다.
- **폴더 탐색**: 워크스페이스 내 `.gemini/skills/` (혹은 `.agents/skills/`) 또는 전역 경로 `~/.gemini/skills/`에 저장된 폴더를 직접 조회할 수 있습니다.

### ③ 서브 에이전트(Sub-Agents) 확인
격리된 컨텍스트에서 특정 태스크를 전문적으로 수행하는 하위 요원 목록입니다.
- **대화형 세션 내부**: `/agents` 명령어를 통해 실시간으로 활성화 상태를 관리할 수 있습니다.
- **폴더 탐색**: `.gemini/agents/*.md` 또는 `~/.gemini/agents/*.md` 경로에서 에이전트 정의 마크다운 파일을 확인하여 세부 기능(System Prompt, Model, Tool)을 살펴볼 수 있습니다.

### ④ 슬래시 명령어(Slash Commands) 및 도움말 확인
- **도움말**: 대화형 모드 창에 `/help`를 입력하면 Antigravity IDE 내부에서 제공하는 모든 내장 슬래시 명령어의 매뉴얼을 열람할 수 있습니다.
- **커스텀 명령어**: 사용자 정의된 명령어를 다시 반영하고 싶을 때는 `/commands reload` 명령을 실행할 수 있습니다.

> [!IMPORTANT]
> **설정 파일 검토**
> 현재 설정된 프로젝트 및 에이전트 권한은 프로젝트 루트 내의 `.gemini/settings.json` 또는 `policy.toml` 파일에서 가장 정확하게 확인하고 제어할 수 있습니다.

---

## 4. 에이전트 권한 제어 (Settings / Permissions)

Antigravity IDE는 에이전트가 로컬 시스템과 코드베이스에 가할 수 있는 권한 범위를 제어하여 보안을 극대화할 수 있는 설정 메뉴를 제공합니다.

### ① 설정 진입 및 위치
- **접근 방법**: `Cmd + ,` (Windows/Linux는 `Ctrl + ,`) 단축키를 누르거나, 화면 좌측 하단의 톱니바퀴(Settings) 아이콘을 클릭하여 설정으로 진입한 후 **Permissions** 메뉴를 선택합니다.

### ② 3가지 작동 제어 방식 (Permission Tiers)
에이전트가 도구나 셸 명령을 실행할 때 다음과 같은 승인 단계를 설정할 수 있습니다.
- **Allow (허용)**: 사용자 승인 절차 없이 에이전트가 해당 도구나 명령을 즉시 자동 실행합니다.
- **Ask (요청)**: 에이전트가 작업을 일시 중지하고, 에디터에 승인 요청 카드를 띄워 사용자의 명시적인 승인을 요구합니다. (기본 권장 설정)
- **Deny (차단)**: 에이전트의 접근 권한을 완전히 금지하여 도구 사용을 원천 차단합니다.

### ③ 대표적인 설정 영역
- **Terminal Execution Policy**: 에이전트의 터미널 명령어 실행 권한 수준(Always Ask / Auto / Turbo 등) 설정
- **JavaScript Execution Policy**: 브라우저 오토메이션 도구 등에서의 자바스크립트 실행 허용 범위 조절
- **File Access Policy**: 프로젝트 범위 밖의 파일이나 `.gitignore` 등록 디렉터리에 대한 접근 제한 설정

---

## 5. 사용량 및 비용 확인 방법 (How to Check Usage & Costs)

Antigravity IDE 및 CLI의 토큰 소모량과 남은 할당량을 효율적으로 추적하는 방법입니다.

### ① 대화 세션 내부에서 즉시 확인 (`/stats`)
대화형 CLI 또는 채팅 인터페이스에서 다음 명령어를 입력하면 현재 세션의 상세 사용 통계가 출력됩니다.
```bash
/stats
```
- **Input Tokens**: 이번 대화 세션에서 AI에 새로 입력된 토큰 수
- **Cached Tokens**: 자동 토큰 캐싱(Token Caching)이 적용되어 **비용이 청구되지 않고 재사용된** 토큰 수
- **Total Token Count**: 캐시를 포함해 해당 세션에서 처리된 누적 컨텍스트 크기

### ② IDE GUI 화면에서 확인 (할당량 모니터링)
- **우측 하단 할당량 표시기**: IDE 창의 우측 하단에 있는 할당량 아이콘/텍스트를 클릭하면 전체 사용량 대시보드로 이동합니다.
- **이중 할당량 구조(Dual-layer Quota)**:
  - **Sprint (5시간 단위)**: 짧은 시간 동안 고강도로 소모된 단기 사용량을 모니터링합니다.
  - **Marathon (일주일 단위)**: 7일 동안 소모한 전체 기본선 사용량을 추적합니다.

### ③ 외부 커뮤니티 도구를 활용한 모니터링
추가적으로 다중 계정이나 깊이 있는 사용 통계를 조회하려는 경우 외부 유틸리티를 활용할 수 있습니다.
- **Antigravity-Usage (CLI)**: 터미널에서 간편하게 할당량을 조회할 수 있는 CLI 도구
- **Antigravity Cockpit / Altimeter (Extensions)**: 상세한 시각적 위젯과 주간 통계 리포트를 보여주는 익스텐션


