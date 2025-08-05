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
- **4중 인증 흐름 설계 및 구현**
  - 유저: JWT + bcrypt / 관리자: 세션 + Argon2
  - 로그인 API 하나로 통합 처리 (is_admin + role 기반 인증 분기)
  - 로그인 실패, 탈퇴/휴면/정지 상태일 경우 차단 및 자동 로그아웃
- **관리자 권한 분리 및 실시간 세션 제어**
  - is_admin + role 값으로 관리자 권한 분기 (마스터/보안/유저 관리자 등)
  - 로그인 시 세션 ID 저장 → 마스터 관리자가 특정 세션 강제 종료 가능
- **보안 미들웨어 구현**
  - 로그인 실패 감지
  - 빠른 요청 탐지
  - XSS / SQL Injection 감지 및 차단 로그 저장
- **Shell Script + crontab 기반 자동 배포 구성**
  - start_all.sh 작성 (백엔드 JAR 종료/재시작 + 프론트 build/start 자동화)
  - EC2 재부팅 시 crontab @reboot 등록으로 서비스 자동 실행
  - 기존 117초 → 26초로 전체 서비스 구동 시간 단축
- **공격 도구 기반 실전 보안 테스트 수행**
  - Hydra로 세션 로그인 대상 무작위 대입 공격 시도 → json 형식이라 히드라 적용 안됨
  - ffuf로 JWT 기반 유저 로그인 공격 시도 → 많은 요청 리미트 로직 x, 무작위 대입공격 성공 및 dos급 공격 성공 → 미들웨어에 빠른요청 탐지 적용
  - curl 기반 반복 요청으로 Rate Limit 미적용 상태 확인 후 제한 미들웨어 적용
  - TruffleHog를 통해 Git 민감정보 유출 여부 사전 점검

---

## 주요 트러블슈팅 사례

- 트러블슈팅1:
  - 문제: ffuf, Hydra 등 공격 도구 사용 시 요청 폭주로 서버 메모리 과부하 발생 
  - 원인: 로그인 시 Argon2의 고비용 연산 + 빠른 요청으로 인해 CPU 100% 도달
  - 해결: 요청 속도 제한(rate limiter), 빠른 요청 감지 미들웨어, 리퀘스트 딜레이 삽입, 공격 로그 저장 및 IP 차단 구조 미들웨어 적용

- 트러블슈팅 2: 
  - 문제: EC2 서버에서 java -jar 실행 시 시간대 문제로 로직 오작동 발생 (예: 이틀 전 날짜로 저장) 
  - 원인: 기본 시스템 시간대가 UTC로 설정되어 있었고, Spring은 이 시간 기준으로 처리 
  - 해결: -Duser.timezone=Asia/Seoul 옵션을 java 실행 시 명시하여 정상 작동

- 트러블슈팅 3: 
  - 문제 : EC2 인스턴스 재부팅 시, 백엔드(Spring Boot)와 프론트(Next.js) 기동까지 총 117초(1분 51초) 소요됨 
  - 원인 : 백/프론트가 하나의 스크립트에서 순차 실행되고, 프론트는 매번 npm install, npm run build를 불필요하게 반복 수행함 
  - 해결 : start_all.sh에서 백/프론트 병렬 실행(& + wait),. node_modules, .next 존재 여부 확인 후 불필요한 작업 생략, crontab @reboot 등록으로 자동 실행 → 최종 서비스 도달 시간 26초, 기존 대비 77% 속도 단축
   
---

## 🔗 관련 링크
- [GitHub](https://github.com/joyulbi/HALO_SHOP)
- [AWS 배포](http://43.202.189.108/)
- [YouTube 시연 영상](https://www.youtube.com/watch?v=Xm-JVtveUPE)

---

# 📌 HALO – 팬 커뮤니티 기반 SNS  
> 2차 팀 프로젝트 (2025.05 ~ 2025.06)

> 회원, 인증, 결제 전담 (Backend)  
> Node.js + Express + Sequelize + MySQL + React + AWS EC2

---

## 🔧 주요 역할 및 구조

- 유저 전용 인증 및 계정 관리 로직 설계
- 상태값 기반 로그인 차단 및 관리 기능 구현
- 이메일 인증 기반 임시 비밀번호 발급 시스템 개발
- 카카오페이 연동 결제 시스템 및 멤버십 등급 반영 기능
- AWS EC2 배포 및 PM2/Nginx 리버스 프록시 구성

---

## 🔐 인증 & 계정 시스템

| 항목 | 내용 |
|------|------|
| 인증 방식 | `passport-local` 기반 세션 인증 |
| 해싱 알고리즘 | `bcrypt` |
| 사용자 상태 제어 | `user_status_id` 필드로 로그인 차단 처리 |
| 자동 로그인 차단 | 세션 존재 여부로 체크 |
| 이메일 인증 기능 | 비밀번호 재발급 시 사용 (임시 PW 발송 후 변경 유도) |
| 복구 기능 | 탈퇴 계정 복구, 휴면 복구 (이메일 기반) |

---

## 💳 결제 시스템

- 카카오페이 결제 연동 API 직접 구현
- 결제 성공 시 `user_payment` 테이블에 기록
- 상태값 `status` 기반으로 결제 성공/실패 관리
- 결제 내역 기반 `membership_id` 변경 처리 (등급 상승)

---

## 🧠 관리자 권한 분기

| 필드 | 설명 |
|------|------|
| `role` | 숫자 기반 관리자 권한 구분 (1~10) |
| 접근 제한 | `roleMiddleware`에서 특정 관리자 role만 통과 허용 |
| 분기 예시 | 유저관리자(5), 보안관리자(6), 마스터(1) 등 |

---

## 🛡 보안 및 상태 체크 미들웨어

- 비정상 상태 유저 차단 로직 구현  
  (`user_status_id`: 2=탈퇴, 3=정지, 4=휴면 → 로그인 거부)
- 자동 탐지 차단은 미구현, 다만 상태 체크 로직은 미들웨어화하여 인증 흐름 제어
- 관리자 전용 경로는 `roleMiddleware`로 보호

---

## 📂 기술 요약

| 구분 | 내용 |
|------|------|
| 인증 | 세션 기반 로그인 (passport) |
| 해싱 | bcrypt |
| 이메일 인증 | 임시 비밀번호 발급 |
| 로그인 차단 | 상태값 기반 분기 (`user_status_id`) |
| 결제 | 카카오페이 API 연동 |
| 배포 | EC2 + PM2 + Nginx |
| 관리자 구조 | `role` 기반 미들웨어 분리 |
| 보안 로직 | 차단 아님, 상태 체크 위주 |
| 사용한 DB | MySQL (Sequelize ORM) |
---
## 주요 트러블 슈팅 사례 
- 트러블슈팅 1: 
  - 문제: 일정 시간이 지나면 soft delete 데이터가 계속 DB에 남아있어 정리 안 됨
  - 원인: 삭제 예약된 계정에 대한 자동 제거 로직이 없었음
  - 해결: Node.js에서 node-cron + MySQL deleted_at 타임스탬프 조건 기반으로 자동 삭제 스케줄러 구현 
 
- 트러블슈팅 2: 
  - 문제: 유저 하드딜리트 시 FK 연관된 테이블이 남아서 삭제 실패 
  - 원인: Sequelize에서 CASCADE 옵션이 누락 및 연관 테이블 처리 순서가 잘못됨 
  - 해결: FK 관계 명확히 설정 + 삭제 순서를 transaction으로 묶어 안전하게 처리
  
---
### 🔗 관련 링크

- [GitHub - HALO 프로젝트](https://github.com/IN-P/HALO)


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
