# 👋 About Me

![Logic](https://img.shields.io/badge/System_Logic-ON-blue?style=flat-square)
![Security](https://img.shields.io/badge/Security-HIGH-critical?style=flat-square)
![Upgrade](https://img.shields.io/badge/Growth-Daily-success?style=flat-square)

안녕하세요, 로직부터 배포까지 **흐름을 직접 설계하는 백엔드 개발자 안윤기**입니다.

시스템은 믿을 수 있는 구조 위에서만 돌아간다고 믿습니다.  
그래서 저는 코드보다 먼저 **전체 흐름을 설계**하고,  
장애 발생 시에는 **로그부터 구조까지 끝까지 추적**합니다.

그리고 그 모든 과정은 결국 **성장으로 연결**된다고 생각합니다.


####  주요 경험 및 기술

- 🌱 **CS 기반 구조 설계** 및 실무 수준의 아키텍처 구성  
- 🛡️ **4중 인증 기반 하이브리드 구조 구현**  
  (유저: JWT + bcrypt / 관리자: 세션 + Argon2 / 로그인 상태 자동 판단 포함)  
- ☁️ **AWS EC2 + S3 + Nginx + Shell Script 기반 배포 자동화**  
- 🔐 **보안 감수성 기반 미들웨어 및 이상행동 대응 로직 설계**  
- 🧠 **장애 발생 시 전체 흐름, 로그, 구조 단위까지 추적하는 습관화**


---

## 📬 CONTACT & LINKS

| 구분 | 내용 |
|------|------|
| Email | zgha16@gmail.com |
| GitHub | https://github.com/yoon0416 |

---

## 🏆 Awards

🥇 **육군군수사령부 디지털 대전환 아이디어 공모전** (2023.07)  
- 전·평시 탄약 적송 자동화 시스템 설계로 사령부 최우수상 수상  
- 개념설계 및 구조화, 전군 확장 가능성 입증  

---

## 🛠 기술 역량 (Tech Stack)

| 영역             | 기술 및 도구 |
|------------------|-------------------------------------------------------------------------------------------------------------------|
| **Backend**      | Java, Spring Boot, Spring Security, MyBatis, JPA, Node.js, Python, REST API, OAuth2, @PreAuthorize |
| **Frontend**     | React, Next.js, Redux, Axios, Styled-components |
| **Infra & 보안** | AWS EC2, S3, Nginx, PM2, Linux, Shell Script, crontab, ffuf, Hydra, TruffleHog, curl |
| **Database**     | MySQL, MyBatis, Sequelize, Soft Delete, Backup Table, node-cron |
| **CI/CD**        | Shell Script + crontab 자동화 (서비스 구동 시간 117s → 26s 단축) |


Back-End : <img src="https://img.shields.io/badge/SpringBoot-6DB33F?style=flat&logo=springboot&logoColor=white"/><img src="https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/MyBatis-000000?style=flat&logo=apache&logoColor=white"/> <img src="https://img.shields.io/badge/JPA-59666C?style=flat&logo=hibernate&logoColor=white"/>

Front-End : <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black"/><img src="https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white"/><img src="https://img.shields.io/badge/Redux-764ABC?style=flat&logo=redux&logoColor=white"/><img src="https://img.shields.io/badge/Axios-5A29E4?style=flat&logo=axios&logoColor=white"/>

Infra / DevOps : <img src="https://img.shields.io/badge/AWS EC2-FF9900?style=flat&logo=amazonaws&logoColor=white"/><img src="https://img.shields.io/badge/AWS S3-569A31?style=flat&logo=amazonaws&logoColor=white"/><img src="https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black"/><img src="https://img.shields.io/badge/Shell Script-4EAA25?style=flat&logo=gnubash&logoColor=white"/><img src="https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white"/>

Auth / Security : <img src="https://img.shields.io/badge/JWT-000000?style=flat&logo=jsonwebtokens&logoColor=white"/><img src="https://img.shields.io/badge/Bcrypt-121212?style=flat&logo=security&logoColor=white"/><img src="https://img.shields.io/badge/Argon2-33AADD?style=flat&logo=veracrypt&logoColor=white"/><img src="https://img.shields.io/badge/Security Testing Tools-000000?style=flat&logo=kali-linux&logoColor=white"/>

---

## 📌 Projects
> 확인하고 싶은 프로젝트를 클릭해주세요!

---

<details>
<summary>🔹 HALO_SHOP – 굿즈 쇼핑몰 & 팬 커뮤니티 (2025.06 ~ 07)</summary>

**담당:** 회원/보안/인증 시스템 전담, EC2 인프라 구성, 자동 배포, 트러블슈팅 및 문서화  

### 🧰 사용기술

| 영역     | 기술 |
|----------|------|
| Frontend | React, Next.js, Redux, Styled-components, SockJS, StompJS, Recharts, Axios |
| Backend  | Spring Boot, Java 11, MyBatis, JPA, Spring Security, OAuth2, WebSocket |
| Infra    | AWS EC2, S3, Nginx, PM2, Shell Script, crontab |
| DB       | MySQL 8.x (Soft Delete, backup table, node-cron 기반 스케줄링) |
| 보안도구 | Hydra, ffuf, TruffleHog, curl, Nikto 등 |

### 📌 주요 기능

- 4중 인증 구조 (JWT + bcrypt / 세션 + Argon2)
- 관리자 권한 분기 및 세션 강제 종료 기능
- 보안 미들웨어로 XSS, SQL Injection, 빠른 요청 차단
- Shell Script 기반 자동 배포 (117s → 26s 단축)
- 실전 보안 도구(ffuf, Hydra 등) 기반 공격 대응 구조 설계

### 🔧 주요 트러블슈팅

- 요청 폭주 → rate limiter + IP 차단
- UTC 시간 설정 → `-Duser.timezone=Asia/Seoul`
- 프론트 비효율적 빌드 반복 → 조건 분기 + 병렬 실행 최적화

### 🤝 협업 및 회고

- 역할 분담 기반 개발 및 문서화 주도 (API 명세서, ERD 등)
- 피드백 기반 응답 포맷 통일 (isAdmin, role)
- 회의록/협업 툴 기반 커뮤니케이션 능동적 참여

### 🔗 링크

- [GitHub](https://github.com/joyulbi/HALO_SHOP)  
- [배포](http://43.202.189.108/)  
- [시연 영상](https://www.youtube.com/watch?v=Xm-JVtveUPE)

</details>

---

<details>
<summary>🔹 HALO – 팬 SNS 기반 커뮤니티 (2025.05 ~ 06)</summary>

**담당:** 회원/인증/결제 시스템, 상태 차단, 이메일 인증, EC2 배포 및 리버스 프록시 구성

### 🧰 사용기술

| 영역     | 기술 |
|----------|------|
| Frontend | React, Redux, Axios |
| Backend  | Node.js, Express, Passport, bcrypt, Nodemailer |
| Infra    | AWS EC2, PM2, Nginx |
| DB       | MySQL 8.x (Soft Delete, deleted_users 테이블) |
| 보안기반 | 이메일 인증, 상태 기반 로그인 차단, 관리자 권한 분기(role 기반) |

### 📌 주요 기능

- 세션 기반 인증 (`passport-local`), bcrypt 해싱
- 탈퇴/정지/휴면 계정 차단
- 이메일 인증 기반 임시 비밀번호 발급 및 복구
- 카카오페이 결제 시스템 구현 및 멤버십 등급 반영
- 관리자 role 기반 접근 제한 미들웨어 설계

### 🔧 트러블슈팅

- Soft delete 계정 정리 누락 → node-cron 기반 자동 제거 구현
- FK 제약으로 인한 삭제 실패 → 트랜잭션 + CASCADE 처리

### 🔗 링크

- [GitHub](https://github.com/IN-P/HALO)

</details>

---

<details>
<summary>🔹 SSGFC – SSG 랜더스 팬 커뮤니티 (2025.04 ~ 05)</summary>

**담당:** 인증/보안/로그 시스템, 관리자 기능, 크롤링, 외부 API 연동, 트러블슈팅 및 보안 문서화

### 🧰 사용기술

| 영역     | 기술 |
|----------|------|
| Frontend | Thymeleaf, Bootstrap, JavaScript |
| Backend  | Java 11, Spring Boot 2.7.14, Spring Security, JPA |
| DB       | MySQL 8.0 |
| Infra    | 로컬 Tomcat → AWS EC2 이전 준비 중 |
| 인증/보안 | Spring Security 커스텀 로그인, OAuth2, 이메일/전화 인증 |
| 외부 API | CoolSMS, Google SMTP, Kakao 주소 API, 기상청 초단기 API |
| 기타     | Jsoup 기반 HTML 크롤링 |

### 📌 주요 기능

- 소셜 로그인(OAuth2), 이메일·전화 인증 통합
- 관리자 권한 분리 및 접근 제어 (@PreAuthorize)
- 게시글/댓글 본인 인증, 비로그인 차단
- 로그 자동 수집 및 30일 보존 스케줄링
- 구조적 보안 설계 + 외부 API 활용

### 🔗 참고 문서

- [보안 설계 문서](https://github.com/yoon0416/ssgpack/blob/main/시큐리티.md)
- [트러블슈팅 문서](https://github.com/yoon0416/ssgpack/blob/main/트러블슈팅.md)
- [문서 저장소](https://github.com/yoon0416/document)
- [AWS 설정](https://github.com/yoon0416/ssgpack/blob/main/aws.md)
- [시연 영상](https://youtu.be/pWBEOX9JKqc)

</details>

---

## 💼 경력 및 활동 요약

- HALO_SHOP, HALO, SSGFC 등 **3개 팀 프로젝트에서 회원/보안/인증 전담**  
- 모든 프로젝트 **AWS EC2 + Nginx + S3 + PM2 운영 및 배포 완료**  
- 관리자 강제 로그아웃, Argon2 해싱, 이메일 인증 기반 복구 등 **보안 로직 직접 구현**  
- JANUS 보안 아키텍처 논문 설계 및 시뮬레이션 기반 보안 흐름 설계  
- 리눅스 Shell Script 자동화, 로그 분석, crontab 기반 스케줄링 경험 보유

---

## 📈 GitHub 활동 요약

![Profile 3D Card](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=yoon0416&theme=vue)

- 1,300회 이상 커밋  
- 90건 이상 Pull Request  
- 외부 기여 레포지토리:
  - [HALO_SHOP](https://github.com/joyulbi/HALO_SHOP)
  - [HALO](https://github.com/IN-P/HALO)

---

## ⭐ 평가 가능한 장점 (Strengths)

- **상황 해결 중심**: 설계 레벨에서 문제 원인을 추적하고 구조로 대응  
- **보안 감수성**: 인증·공격 시나리오·테스트·침투 대응 경험  
- **문서화 역량**: README, 배포 가이드, 트러블슈팅 정리 습관  
- **시스템 구조 이해**: 팀 전체 흐름과 역할 파악에 강점  

---

## 💡 Career Goals

- 설계에 기반한 기술 도입 및 구조적 확장 가능성 추구  
- Linux, SQL, AWS 기반으로 실용 중심 백엔드 성장  
- 보안 탐지 및 로그 설계 고도화 → 실전 대응 가능한 보안 시스템 구현  
- 다양한 인증/보안 도구를 커스터마이징할 수 있는 보안 개발자 지향

