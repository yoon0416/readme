# 👋 About Me

안녕하세요, 흐름을 먼저 설계하고 끝까지 책임지는 백엔드 개발자 **안윤기**입니다. <br>
저는 시스템의 신뢰는 '정확한 로직과 단단한 구조'에서 시작된다고 믿습니다.

- 🌱 CS 기반 구조 이해 및 실무 설계 경험
- 🛡️ JWT + 세션 혼합 하이브리드 인증 구조 구현
- ☁️ AWS EC2 + S3 + Nginx + Shell Script 배포 및 인프라 구축
- 🔐 보안 감수성 기반 미들웨어 및 공격 대응 로직 설계
- 🧠 구조부터 로그 추적까지, 장애 시 전방위 분석 습관

---

## 📬 CONTACT & LINKS

| 구분 | 내용 |
|------|------|
| Email | zgha16@gmail.com |
| GitHub | https://github.com/yoon0416 |
---

## 🏆 Awards
🥇 **육군군수사령부 디지털 대전환 아이디어 공모전** (2023.07)
- → 전·평시 탄약 적송 자동화 시스템 설계로 사령부 최우수상 수상
- → 개념설계 및 구조화, 전군 확장 가능성 입증


---

## 🛠 기술 역량 (Tech Stack)
[![기술스택](https://github-readme-stats.vercel.app/api/top-langs/?username=yoon0416&layout=compact&hide=html)](https://github.com/anuraghazra/github-readme-stats)


**Backend**  
- Java, Spring Boot, Spring Security, MyBatis, JPA, Node.js, python  
- Session + JWT 혼합 인증 구조, Argon2, bcrypt  
- Rest API, @PreAuthorize, OAuth2  

**Frontend**  
- React, Next.js, Redux, Axios  
- JWT 저장/삭제 도메인 관리, 상태관리 설계  

**Infra & Security**  
- AWS EC2, S3, Nginx, PM2, Linux(Ubuntu), crontab, .sh script  
- ffuf, Hydra, TruffleHog, curl 등 보안 테스트 도구  

**Database**  
- MySQL, MyBatis, Sequelize  
- Soft Delete/구성 backup table, scheduler  

**CI/CD**  
- Shell Script + crontab 기반 자동 배포 스크립트 (117s → 26s)

---
## GitHub 활동 요약
[![yoon's GitHub stats](https://github-readme-stats.vercel.app/api?username=yoon0416)](https://github.com/anuraghazra/github-readme-stats)


- 2025년 기준 약 1,300회 이상 커밋하며 꾸준한 Git 기반 개발 활동 경험
- 90건 이상의 Pull Request를 통해 협업 중심 개발 환경에 익숙함
- 외부 레포지토리 2곳 이상 기여 경험 보유
  - [쇼핑몰 프로젝트](https://github.com/joyulbi/HALO_SHOP)
  - [SNS 프로젝트](https://github.com/IN-P/HALO)



---

## 📌 Projects

### 🔹 HALO_SHOP – 굿즈 쇼핑몰 & 팬 커뮤니티 (2025.06 ~ 07)
> 🛠 담당: 회원/보안/인증 시스템 전담, EC2 인프라 구성 및 자동 배포 / 트러블슈팅 및 팀 프로젝트 README.md 문서화

## 사용기술
| 영역       | 기술 스택                                                                      |
| -------- | -------------------------------------------------------------------------- |
| Frontend | React, Next.js, Redux, Styled-components, SockJS, StompJS, Recharts, Axios |
| Backend  | Spring Boot, Java 11, MyBatis, JPA, Spring Security, OAuth2, WebSocket     |
| Infra    | AWS EC2, S3, Nginx, PM2, crontab, Shell Script                             |
| DB       | MySQL 8.x (Soft Delete, backup table, node-cron 기반 스케줄링)                   |
| 보안도구     | Hydra, ffuf, TruffleHog, curl, Nikto 등 실전 테스트                              |


## 주요 기능
- 4중 인증 흐름 설계 및 구현
  - 유저: JWT + bcrypt / 관리자: 세션 + Argon2
  - 로그인 API 하나로 통합 처리 (is_admin + role 기반 인증 분기)
  - 로그인 실패, 탈퇴/휴면/정지 상태일 경우 차단 및 자동 로그아웃
- 관리자 권한 분리 및 실시간 세션 제어
  - is_admin + role 값으로 관리자 권한 분기 (마스터/보안/유저 관리자 등)
  - 로그인 시 세션 ID 저장 → 마스터 관리자가 특정 세션 강제 종료 가능
- 보안 미들웨어 구현
  - 로그인 실패 감지
  - 빠른 요청 탐지
  - XSS / SQL Injection 감지 및 차단 로그 저장
- Shell Script + crontab 기반 자동 배포 구성
  - start_all.sh 작성 (백엔드 JAR 종료/재시작 + 프론트 build/start 자동화)
  - EC2 재부팅 시 crontab @reboot 등록으로 서비스 자동 실행
  - 기존 117초 → 26초로 전체 서비스 구동 시간 단축
- 공격 도구 기반 실전 보안 테스트 수행
  - Hydra로 세션 로그인 대상 무작위 대입 공격 시도 → json 형식이라 히드라 적용 안됨
  - ffuf로 JWT 기반 유저 로그인 공격 시도 → 많은 요청 리미트 로직 x, 무작위 대입공격 성공 및 dos급 공격 성공 → 미들웨어에 빠른요청 탐지 적용
  - curl 기반 반복 요청으로 Rate Limit 미적용 상태 확인 후 제한 미들웨어 적용

TruffleHog를 통해 Git 민감정보 유출 여부 사전 점검

🧩 주요 트러블슈팅 사례
- 관리자 로그인 실패
→ 로그인 응답에서 isAdmin, role, session 여부 누락 → JSON 응답 구조 재정의
- WebSocket이 Next.js dev 모드에서 작동 안 됨
→ npm run dev 환경에서는 정상 작동 불가 → build 후 실행으로 해결
- 시간대 오류로 EC2 배포 시 날짜 -2일 오류 발생
→ -Duser.timezone=Asia/Seoul 파라미터 명시
- pm2 없이 Node+Java 병렬 자동 배포 구현
→ start_all.sh에 병렬 처리 및 skip 조건 추가, crontab 등록 완료
- ffuf/Hydra 공격 시 CPU 100% 이상 도달
→ 요청 간 delay 삽입, 빠른 요청 차단 미들웨어 설계, 공격자 IP 로그 저장
- 이미지 경로 대소문자 오류 (Linux 배포 환경)
→ .PNG, .Png 등 혼용 → 모든 경로 및 파일명 .png로 통일 처리

## 🔗 관련 링크
- [GitHub](https://github.com/joyulbi/HALO_SHOP)
- [AWS 배포](http://43.202.189.108/)
- [YouTube 시연 영상](https://www.youtube.com/watch?v=Xm-JVtveUPE)

---

### 🔹 HALO – 팬 커뮤니티 SNS (2025.05 ~ 06)
> 🛠 담당: 회원/보안/인증/결제 파트 전담  
> ⚙️ Node.js + Sequelize + React 

- JWT 로그인 + 세션 기반 관리자 인증 구조 분리 설계
- 회원가입, 로그인, 정지/휴면/탈퇴 상태 제어 및 접근 차단
- 탈퇴 복구 및 비밀번호 재발급 기능 (이메일 인증 기반) 직접 구현
- 카카오페이 결제 기능 및 멤버십 등급 상태 관리 기능 직접 구현
- 공격 탐지용 로그 수집 로직 설계 및 Postman 테스트 자동화
- 관리자 권한(role) 기반 미들웨어 구현 (마스터/보안/유저 관리자)
- 👉 [GitHub](https://github.com/IN-P/HALO)

---

### 🔹 SSGFC – 야구 커뮤니티 (2025.04 ~ 05)
> 🛠 담당: 회원/보안/관리자 기능 담당  
> ⚙️ Spring Boot + JPA + MySQL

- 회원가입, 로그인, 마이페이지, Soft Delete 기반 탈퇴 처리 구현
- 관리자 권한 분리 설계 및 유저 제어 기능 구현 (상태값 기반 제어)
- JWT 기반 인증 및 logs 테이블 구축, 비정상 요청 차단 로직 추가
- 👉 [GitHub](https://github.com/yoon0416/SSGFC)





---
## 💼 경력 및 활동
- 보안 중심 백엔드 개발자로 다수 팀 프로젝트에 참여
  - SSGFC(야구 커뮤니티), HALO(팬 SNS), HALO_SHOP(굿즈 쇼핑몰) 프로젝트에서 <br>
    → 회원/보안/인증/결제 시스템 전체 설계 및 구현 담당
    
- 3개 팀 프로젝트 모두 실제 배포까지 완료, AWS EC2 + Nginx + S3 + PM2 등 직접 운영

- JWT + 세션 하이브리드 인증, Argon2 관리자 해싱, 로그인 차단 로직, 계정 상태 제어, 이메일 인증 기반 복구 및 비밀번호 초기화, 관리자 강제 로그아웃, 로그 블록체인 설계 등 구현

- 모든 프로젝트에 대해 트러블슈팅 문서화 + 리드미 작성 + 배포 가이드 문서화 경험

- 보안 논문 JANUS 직접 설계 → 구조 기반 판단 아키텍처, Fake DB, 디지털 트윈, KARMA 설계자 감시 시스템 설계

- 리눅스 쉘 스크립트 기반 배포 자동화, crontab 스케줄러 연동 경험 보유

---
## ⭐ 평가 가능한 장점 (Strengths)

- **상황 해소 중심**: 문제 발생 시 설계 단계에서 원인을 파악하고 구조부터 수정  
- **보안 감수성**: 시뮬레이션, 테스트, 인증 로직 설계 능력  
- **문서화 역량**: README, 배포 가이드, 트러블슈팅 정리 습관  
- **업무 구조 이해**: 회사 구조 이해 후 기술 습득 → 팀 생산성 기반으로 확장 가능  

---

## 💡 Career Goals

- 구조적 이해가 가능한 설계 위에 기술 도입  
- 변경이 적은 **Linux, SQL, AWS**를 실용 중심으로 지속 활용  
- 차기 프로젝트에 **보안 감지, 로그 테스트 단계 확장** 계획  
- 다양한 인증/보안 도구를 실전에 맞춰 커스터마이징할 역량 확보 예정  
