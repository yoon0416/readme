# 👋 About Me

> 흐름을 먼저 설계하고 끝까지 책임지는 백엔드 개발자 **안윤기**입니다.

시스템의 신뢰는 **정확한 로직과 단단한 구조**에서 출발한다고 믿습니다.  
**설계 → 구현 → 배포 → 장애 대응**까지, 책임지는 개발을 지향합니다.

---

## 🧠 핵심 역량 요약

- ✅ CS 기반 구조 이해 및 실무 적용 능력  
- 🔐 **4중 인증 기반 하이브리드 인증 구조** 설계  
- ☁️ AWS EC2 + S3 + Nginx + PM2 등 인프라 전담  
- 🛡️ 보안 미들웨어 + 자동 차단 로직 직접 구현  
- 🧾 로그 기반 트러블슈팅 & 보안 설계 문서화 습관  

---

## 🛠 Tech Stack

| 분류 | 기술 |
|------|------|
| **Backend** | Java, Spring Boot, Node.js, Express, MyBatis, JPA, REST API, OAuth2 |
| **Frontend** | React, Next.js, Redux, Styled-components |
| **Infra** | AWS EC2, S3, Nginx, PM2, Shell Script, crontab |
| **Security** | JWT, Session, Argon2, Bcrypt, ffuf, Hydra, curl 등 |
| **Database** | MySQL, Sequelize (Soft Delete, Backup Table) |
| **CI/CD** | Shell Script 기반 자동 배포 (구동 시간 117s → 26s 단축) |

---

## 🏆 수상 이력

- 🥇 **육군군수사령부 디지털 대전환 아이디어 공모전 최우수상**
  - 전·평시 탄약 적송 자동화 시스템 설계
  - 개념 구조화 + 전군 확장 가능성 입증

---

## 📬 연락처 & 링크

| 항목 | 내용 |
|------|------|
| 📧 Email | zgha16@gmail.com |
| 🐙 GitHub | [github.com/yoon0416](https://github.com/yoon0416) |
| 📽️ YouTube | [시연 영상](https://www.youtube.com/watch?v=Xm-JVtveUPE) |
| 🌐 배포 링크 | [HALO_SHOP 배포](http://43.202.189.108/) |

---

## 🔹 대표 프로젝트 요약

---

### 🛒 HALO_SHOP – 굿즈 쇼핑몰 & 팬 커뮤니티  
> `2025.06 ~ 07` ｜ Spring Boot + React + AWS 배포 + 보안 설계  
> **담당:** 회원 인증 · 관리자 기능 · 보안 로직 · EC2 인프라 · 자동배포 · 로그 설계

<details>
<summary>📌 기능 요약 (펼쳐보기)</summary>

- **4중 인증 흐름**: JWT + bcrypt (유저) / Session + Argon2 (관리자)
- is_admin + role 기반 통합 로그인 API
- 보안 미들웨어: 로그인 실패, 빠른 요청, XSS, SQL Injection 탐지 및 차단
- Shell Script + crontab 자동 배포 구성 (117s → 26s)
- ffuf/Hydra/curl 등 도구 기반 실전 보안 테스트 수행 및 대응

</details>

<details>
<summary>🔧 주요 트러블슈팅 사례</summary>

- **문제:** 공격 도구 요청 폭주로 서버 메모리 과부하  
  **해결:** 요청 속도 제한 + 딜레이 삽입 + IP 차단 구조 미들웨어 적용

- **문제:** EC2 시간대 설정 오류로 로직 오작동  
  **해결:** `-Duser.timezone=Asia/Seoul` 옵션 적용

- **문제:** 서버 재시작 시 서비스 도달까지 117초 소요  
  **해결:** start_all.sh 병렬 실행 최적화 → 26초 단축 (77% 개선)

</details>

<details>
<summary>🤝 협업 및 리더십</summary>

- API 명세서, ERD, 배포 가이드 등 문서화 주도  
- 응답 포맷 개선 피드백 수용 → isAdmin/role 포함 통일된 구조로 정비  
- 실시간 이슈 대응 및 커뮤니케이션 주도

</details>

---

### 📱 HALO – 팬 SNS 기반 커뮤니티  
> `2025.05 ~ 06` ｜ Node.js + MySQL + 카카오페이 결제 + 세션 인증  
> **담당:** 회원/인증/결제 시스템, 로그인 상태 차단, 이메일 인증 흐름 설계

<details>
<summary>📌 핵심 구조</summary>

- 세션 기반 인증 (`passport-local`), bcrypt 해싱  
- user_status 기반 로그인 차단 (탈퇴/휴면/정지)  
- 카카오페이 연동 → 결제 기록 + 멤버십 등급 반영  
- 이메일 인증 → 임시 비밀번호 발급 및 복구  
- 관리자 접근 roleMiddleware 설계 및 분기

</details>

<details>
<summary>🔧 트러블슈팅 예시</summary>

- **문제:** soft delete 데이터 정리 안 됨  
  **해결:** node-cron + deleted_at 기반 자동 삭제 스케줄러 구현

- **문제:** FK 연관 테이블 삭제 실패  
  **해결:** CASCADE 누락 + 삭제 순서 오류 → transaction 처리로 해결

</details>

---

### 🧢 SSGFC – 야구 팬 커뮤니티  
> `2025.04 ~ 05` ｜ Spring Boot + Spring Security + OAuth2  
> **담당:** 인증/보안/로그 시스템 설계 + 관리자 기능 + 외부 API 연동

<details>
<summary>📌 주요 기능</summary>

- Spring Security 커스텀 로그인, 세션 기반 인증 구조  
- OAuth2 소셜 로그인 + 이메일/전화 인증 통합  
- @PreAuthorize 기반 관리자 권한 분리  
- 로그 자동 기록 + 30일 삭제 스케줄러 구성  
- Kakao 주소 API, 기상청 API, CoolSMS 등 외부 연동 구현

</details>

---

## 📄 문서 및 자료

- 🔐 [보안 설계 문서](https://github.com/yoon0416/ssgpack/blob/main/시큐리티.md)  
- 🛠 [트러블슈팅 문서](https://github.com/yoon0416/ssgpack/blob/main/트러블슈팅.md)  
- 📚 [문서 저장소](https://github.com/yoon0416/document)  
- ☁️ [AWS 설정 가이드](https://github.com/yoon0416/ssgpack/blob/main/aws.md)  

---

## 💼 활동 이력

- SSGFC / HALO / HALO_SHOP 등 3개 실전 프로젝트에서 **회원/보안/인증 전담**
- **모든 프로젝트 AWS 배포 완료** 및 EC2/S3/Nginx 운영
- 로그인 차단/복구/하이브리드 인증 등 **보안 로직 직접 구현**
- JANUS 보안 논문 설계: Fake DB, 설계자 감시 시스템 등 구조화
- 리눅스 Shell Script 기반 배포 자동화 경험 풍부

---

## ⭐ 강점 요약

- **상황 해결 중심 개발**: 문제의 원인을 구조에서 찾고 해결  
- **보안 감수성**: 침투 시나리오, 로직 테스트, 대응 구조 설계  
- **문서화 습관**: README, 트러블슈팅, 배포가이드 작성  
- **업무 구조 기반 사고**: 시스템 전체의 흐름을 고려한 설계 가능

---

## 💡 Career Goals

- 구조를 이해하고 통제할 수 있는 백엔드 보안 아키텍처 설계자  
- Linux / SQL / AWS 기반 실용적이고 안정적인 기술 중심 성장  
- 로그 테스트 및 인증 흐름 고도화, 자동 공격 탐지 시스템 설계  
- 실전 보안 구조를 커스터마이징할 수 있는 역량 강화

