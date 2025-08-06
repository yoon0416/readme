# 👋 About Me
> 시키는 일만 하는 '직장인'이 아니라, 꾸준히 공부하며 성장하는 '개발자'로 <br>
![Logic](https://img.shields.io/badge/System_Logic-ON-blue?style=flat-square)
![Security](https://img.shields.io/badge/Security-HIGH-critical?style=flat-square)
![Upgrade](https://img.shields.io/badge/Growth-Daily-success?style=flat-square)

안녕하세요, 로직부터 배포까지 **흐름을 직접 설계하는 백엔드 개발자 안윤기**입니다.

시스템은 믿을 수 있는 구조 위에서만 돌아간다고 믿습니다.  
그래서 저는 코드보다 먼저 **전체 흐름을 설계**하고,  
장애 발생 시에는 **로그부터 구조까지 끝까지 추적**합니다.

이 모든 과정은 **개인과 팀, 모두의 성장으로 연결**된다고 생각합니다.  
혼자 앞서가는 개발자가 아닌, 동료와 함께 배우고 문제를 해결하며  
새로운 기술에 도전하는걸 두려워하지 않고 더 나은 시스템과 가치를 만들어가는 개발자로 성장하고 싶습니다.

####  주요 경험 및 기술

-  **CS 기반 구조 설계** 및 실무 수준의 아키텍처 구성  
-  **4중 인증 기반 하이브리드 구조 구현**  
     (유저: JWT + bcrypt / 관리자: 세션 + Argon2 / 로그인 상태 자동 판단 포함)  
-  **AWS EC2 + S3 + Nginx + Shell Script 기반 배포 자동화**  
-  **보안 감수성 기반 미들웨어 및 이상행동 대응 로직 설계**  
-  **장애 발생 시 전체 흐름, 로그, 구조 단위까지 추적하는 습관화**


---

## 📬 CONTACT & LINKS

| 구분 | 내용 |
|------|------|
| Name | 안윤기 |
| Email | zgha16@gmail.com |
| GitHub | https://github.com/yoon0416 |

---

## 🏆 Awards

🥇 **육군군수사령부 디지털 대전환 아이디어 공모전** (2023.07)  
- 전·평시 탄약 적송 자동화 시스템 설계로 사령부 최우수상 수상  
- 개념설계 및 구조화, 전군 확장 가능성 입증  

---

## 🛠 기술 역량 (Tech Stack)

| 영역             | 기술 및 도구                                                                                    | 적용 사례 / 설계 경험                                                  |
| -------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------- |
| **Backend**    | Java, Spring Boot, Spring Security, MyBatis, JPA, Node.js, REST API, OAuth2, @PreAuthorize | 4중 인증 구조 설계 (JWT + 세션), 사용자 상태 기반 로그인 차단, 관리자 인증 분기 설계         |
| **Frontend**   | React, Next.js, Redux, Axios, Styled-components                                            | 로그인/회원가입/결제 UI 구현, 상태관리 및 API 연동, 관리자 전용 페이지 구현                |
| **Infra & 보안** | AWS EC2, S3, Nginx, PM2, Linux, Shell Script, crontab, ffuf, Hydra, TruffleHog, curl     | EC2 배포 자동화, 서버 장애 복구, 보안 미들웨어 + 무작위 대입 공격 탐지, curl을 활용한 서버 로그 기반 보안 점검 |
| **Database**   | MySQL, MyBatis, JPA, Sequelize, Soft Delete, node-cron                                     | 유저 테이블 소프트 딜리트 + 30일 복구 구조, 탈퇴 로그 관리, 회원/결제 관련 테이블 연관관계 설계     |
| **CI/CD**      | Shell Script + crontab                                                                     | EC2 자동 재시작 스크립트 구성, 서버 구동 시간 117s → 26s 단축                     |
| **CS - 네트워크** | TCP/IP, 쿠키/세션, 포트, CORS, 요청/응답 흐름 |RESTful API 기반 프론트-백 연결 구조 설계, CORS 정책 적용 및 인증/요청 헤더 흐름 설계 , 세션/쿠키 기반 인증 처리 경험 |
| **CS - 자료구조** | B-Tree (MySQL 인덱스) | `WHERE` 조건 기반 인덱스 조회로 `O(log N)` 수준의 검색 성능 확보 |
| **CS - 보안**    | XSS, SQL Injection, JWT, 암호화(Bcrypt/Argon2), 인증 흐름 설계  , 세션 인증, OAuth2,                                     | 4중 인증 구조 설계(JWT+Bcrypt / 세션+Argon2), 로그인 상태 자동 판단, 관리자 분기 및 세션 강제 종료 로직, 공격 대응 미들웨어 설계, 관리자 인증 분기, 유저 상태 기반 로그인 차단, 해시 알고리즘 분리 적용       |

<details>
<summary><strong>SQL 조회와 시간복잡도 비교</strong></summary>

<br>

| 항목                | 네가 실제 사용한 쿼리                         | 설명                                                                 | 시간복잡도   |
|---------------------|----------------------------------------------|----------------------------------------------------------------------|--------------|
| WHERE 조건 검색      | `SELECT * FROM account WHERE email = ?`      | `email`에 인덱스가 있으면 MySQL은 **B-Tree** 구조로 탐색 시작              | `O(log N)`   |
| Primary Key 조회     | `SELECT * FROM account WHERE id = ?`         | PK 컬럼은 기본적으로 인덱스가 걸림 → 빠른 탐색 가능                            | `O(log N)`   |
| 정렬 없이 전체 탐색 | `SELECT * FROM account`                      | 인덱스를 사용하지 않고 전체 테이블을 순차 탐색 (Full Table Scan)         | `O(N)`       |

- B-Tree 인덱스란?
     - MySQL(InnoDB)의 기본 인덱스 구조.
     - 균형 잡힌 트리 구조로 되어 있어서, 검색 시 루트 노드 → 중간 노드 → 리프 노드까지 타고 내려가며 빠르게 탐색 가능.
     - 정렬된 상태로 저장되며, 범위 조건 검색에도 유리.
     - 평균 시간복잡도는 O(log N).

- 인덱스가 없다면?
     - SELECT * FROM account처럼 인덱스를 타지 않으면, 테이블 처음부터 끝까지 한 줄씩 확인하는 선형 탐색이 됨.
     - 이 경우 시간복잡도는 O(N), 즉 데이터가 많아질수록 성능 급하락.

#### 사용예시

| 사용 맥락        | 쿼리 예시                                   | 설명                  |
| ------------ | --------------------------------------- | ------------------- |
|  로그인 처리    | `SELECT * FROM account WHERE email = ?` | 이메일 인덱스 기반 빠른 탐색 사용 |
|  관리자 상세 조회 | `SELECT * FROM account WHERE id = ?`    | PK 탐색으로 즉시 조회 가능    |


</details>

<br>

Back-End : <img src="https://img.shields.io/badge/SpringBoot-6DB33F?style=flat&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/MyBatis-000000?style=flat&logo=apache&logoColor=white"/> <img src="https://img.shields.io/badge/JPA-59666C?style=flat&logo=hibernate&logoColor=white"/>

Front-End : <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black"/> <img src="https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white"/> <img src="https://img.shields.io/badge/Redux-764ABC?style=flat&logo=redux&logoColor=white"/> <img src="https://img.shields.io/badge/Axios-5A29E4?style=flat&logo=axios&logoColor=white"/>

Infra / DevOps : <img src="https://img.shields.io/badge/AWS EC2-FF9900?style=flat&logo=amazonaws&logoColor=white"/> <img src="https://img.shields.io/badge/AWS S3-569A31?style=flat&logo=amazonaws&logoColor=white"/> <img src="https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black"/> <img src="https://img.shields.io/badge/Shell Script-4EAA25?style=flat&logo=gnubash&logoColor=white"/> <img src="https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white"/>

Auth / Security : <img src="https://img.shields.io/badge/JWT-000000?style=flat&logo=jsonwebtokens&logoColor=white"/> <img src="https://img.shields.io/badge/Bcrypt-121212?style=flat&logo=security&logoColor=white"/> <img src="https://img.shields.io/badge/Argon2-33AADD?style=flat&logo=veracrypt&logoColor=white"/> <img src="https://img.shields.io/badge/Security Testing Tools-000000?style=flat&logo=kali-linux&logoColor=white"/>

---

##  Projects

<summary>🔹 HALO_SHOP – 굿즈 쇼핑몰 & 팬 커뮤니티 (2025.06 ~ 07)</summary>

**담당:** 회원/보안/인증 시스템 전담, EC2 인프라 구성, 자동 배포, 트러블슈팅 및 문서화  

### 사용기술

| 영역     | 기술 |
|----------|------|
| Frontend | React, Next.js, Redux, Styled-components, SockJS, StompJS, Recharts, Axios |
| Backend  | Spring Boot, Java 11, MyBatis, JPA, Spring Security, OAuth2, WebSocket |
| Infra    | AWS EC2, S3, Nginx, PM2, Shell Script, crontab |
| DB       | MySQL 8.x (Soft Delete, backup table, node-cron 기반 스케줄링) |
| 보안도구 | Hydra, ffuf, TruffleHog, curl, Nikto 등 |

###  주요 기능

- 4중 인증 구조 (JWT + bcrypt / 세션 + Argon2)
     - 같은 로그인 요청 엔드포인트에서 내부 로직을 이용하여 유저/관리자 로그인 분리하고 싶었고 상대적으로 보안이 더 중요한 관리자파트 보안강화
- 관리자 권한 분기 및 세션 강제 종료 기능
     - 관리자 계정 탈취 시 강제 로그아웃을 할 수 있게 기능 구현 및 단순 "관리자니?" 물어보고 끝이 아닌 "어떤관리자니?" 까지 체크하여 보안 강화
- 보안 미들웨어로 XSS, SQL Injection, 빠른 요청 차단
     - 현재 전역에서 미들웨어가 발동중이지만 추후 세세하게 분기 나눌 예정
- Shell Script 기반 자동 배포 (117s → 26s 단축)
- 실전 보안 도구(ffuf, Hydra 등) 기반 공격 대응 구조 설계
     - 직접 테스트 해보고 부족했던 보안정책 강화

###  주요 트러블슈팅

-  **트러블슈팅 1**:
     - 문제: 관리자 로그인 시 일반 유저로 처리되거나 인증 실패
     - 원인: 단일 로그인 API에서 is_admin/role 분기 없이 인증이 실행됨
     - 해결: 로그인 로직을 4단 분기로 설계 (1) 관리자 여부 판단 → (2) 일반: JWT+Bcrypt, 관리자: 세션+Argon2 → (3) 인증 방식 분리 → (4) 전용필터 적용

- **트러블슈팅 2**:
     - 문제: ffuf, Hydra 등 공격 도구 사용 시 요청 폭주로 서버 메모리 과부하 발생
     - 원인: 로그인 시 Argon2의 고비용 연산 + 빠른 요청으로 인해 CPU 100% 도달
     - 해결: 요청 속도 제한(rate limiter), 빠른 요청 감지 미들웨어, 리퀘스트 딜레이 삽입, 공격 로그 저장 및 IP 차단 구조 추후 구현

- **트러블슈팅 3**:
     - 문제: EC2 서버에서 java -jar 실행 시 시간대 문제로 로직 오작동 발생 (예: 이틀 전 날짜로 저장)
     - 원인: 기본 시스템 시간대가 UTC로 설정되어 있었고, Spring은 이 시간 기준으로 처리
     - 해결: -Duser.timezone=Asia/Seoul 옵션을 java 실행 시 명시하여 정상 작동
     - 
- **트러블슈팅 4**:
     - 문제 : EC2 인스턴스 재부팅 시, 백엔드(Spring Boot)와 프론트(Next.js) 기동까지 총 117초(1분 51초) 소요됨
     - 원인 : 백/프론트가 하나의 스크립트에서 순차 실행되고, 프론트는 매번 npm install, npm run build를 불필요하게 반복 수행함
     - 해결 : start_all.sh에서 백/프론트 병렬 실행(& + wait),. node_modules, .next 존재 여부 확인 후 불필요한 작업 생략, crontab @reboot 등록으로 자동 실행 → 최종 서비스 도달 시간 26초, 기존 대비 77% 속도 단축
     - 
- **트러블슈팅 5**:
     - 문제 : 특정 권한이 있는 계정 또는 침입자가 update, delete 쿼리를 이용하여 로그 내용을 조작 혹은 삭제가 가능했음
     - 원인 : 테이블에 대한 조작 방지 로직 미비, 접근 제어로는 충분하지 않으며, SQL 직접 접근 시 차단 수단 없음
     - 해결 : AWS ec2에서 mysql 열고 테이블에 트리거 기반 조작 차단 로직 추가, BEFORE UPDATE, BEFORE DELETE 트리거에서 쿼리 실행 전 예외 발생,SIGNAL SQLSTATE '45000’ 명령으로 MySQL 내부에서 오류 유도, 실행 자체를 차단

###  협업 및 회고

- 인증/보안/결제 기능 분담 개발 + 전체 문서화 주도
- 실시간 이슈 대응 및 일정 조율 → 협업 안정화 경험 확보
- API 응답 포맷 개선(role, isAdmin 통일)
- 목표: 안정성·보안성·유지보수성 고려한 구조 설계 능력 강화
- 회의록/협업 툴 기반 커뮤니케이션 능동적 참여
- aws 배포방법, readme 등 모든 내용 문서화 후 팀원에게 공유

### 🔗 링크

- [GitHub](https://github.com/joyulbi/HALO_SHOP)  
- [관련 보안 테스트 문서정리1](https://github.com/joyulbi/HALO_SHOP/blob/main/%EB%B3%B4%EC%95%88%ED%85%8C%EC%8A%A4%ED%8A%B8%20%ED%88%B4%20%EC%82%AC%EC%9A%A9%20-%20%EC%95%88%EC%9C%A4%EA%B8%B0.md)
- [관련 보안 테스트 문서정리2](https://github.com/joyulbi/HALO_SHOP/blob/main/%EB%B3%B4%EC%95%88%ED%85%8C%EC%8A%A4%ED%8A%B8%20(Linux%20Shell%20Script)%20-%20%EC%95%88%EC%9C%A4%EA%B8%B0.md)
- [관련 보안 테스트 문서정리3](https://github.com/joyulbi/HALO_SHOP/blob/main/%EB%B3%B4%EC%95%88%ED%85%8C%EC%8A%A4%ED%8A%B8%20(Hydra%20%26%20ffuf)%20-%20%EC%95%88%EC%9C%A4%EA%B8%B0.md)
- [배포](http://43.202.189.108/)
- [배포 강의문서](https://github.com/yoon0416/document/blob/main/AWS_HALOSHOP.md)
- [시연 영상](https://www.youtube.com/watch?v=Xm-JVtveUPE)




---


<summary>🔹 HALO – 팬 SNS 기반 커뮤니티 (2025.05 ~ 06)</summary>

**담당:** 회원/인증/결제 시스템, 상태 차단, 이메일 인증, EC2 배포 및 리버스 프록시 구성

###  사용기술

| 영역     | 기술 |
|----------|------|
| Frontend | React, Redux, Axios |
| Backend  | Node.js, Express, Passport, bcrypt, Nodemailer |
| Infra    | AWS EC2, PM2, Nginx |
| DB       | MySQL 8.x (Soft Delete, deleted_users 테이블) |
| 보안기반 | 이메일 인증, 상태 기반 로그인 차단, 관리자 권한 분기(role 기반) |

###  주요 기능

- 세션 기반 인증 (`passport-local`), bcrypt 해싱
- 탈퇴/정지/휴면 계정 차단
- 이메일 인증 기반 임시 비밀번호 발급 및 복구
- 카카오페이 결제 시스템 구현 및 멤버십 등급 반영
- 관리자 role 기반 접근 제한 미들웨어 설계

### 주요 트러블슈팅

- **트러블슈팅 1**:
     - 문제: 일정 시간이 지나면 soft delete 데이터가 계속 DB에 남아있어 정리 안 됨
     - 원인: 삭제 예약된 계정에 대한 자동 제거 로직이 없었음
     - 해결: Node.js에서 node-cron + MySQL deleted_at 타임스탬프 조건 기반으로 자동 삭제 스케줄러 구현

- **트러블슈팅 2**:
     - 문제: 유저 하드딜리트 시 FK 연관된 테이블이 남아서 삭제 실패
     - 원인: Sequelize에서 CASCADE 옵션이 누락 및 연관 테이블 처리 순서가 잘못됨
     - 해결: FK 관계 명확히 설정 + 삭제 순서를 transaction으로 묶어 안전하게 처리


###  협업 및 회고

- 인증/결제/보안 파트 분담 개발 + _app.js 구조 충돌 분석 및 병합 조율
- 명세 문서/README 정리 주도 → 팀 전체 코드 이해도 향상
- 협업/문제해결/설계까지 고려하는 백엔드 엔지니어로 성장 중
- 목표: 로그 기반 대시보드 + AI 보안 탐지 + 고급 인증 구조 설계
- aws 배포방법, readme 등 모든 내용 문서화 후 팀원에게 공유

### 🔗 참고 문서

- [GitHub](https://github.com/IN-P/HALO)



---


<summary>🔹 SSGFC – SSG 랜더스 팬 커뮤니티 (2025.04 ~ 05)</summary>

**담당:** 인증/보안/로그 시스템, 관리자 기능, 크롤링, 외부 API 연동, 트러블슈팅 및 보안 문서화

###  사용기술

| 영역     | 기술 |
|----------|------|
| Frontend | Thymeleaf, Bootstrap, JavaScript |
| Backend  | Java 11, Spring Boot 2.7.14, Spring Security, JPA |
| DB       | MySQL 8.0 |
| Infra    | 로컬 Tomcat → AWS EC2 이전 준비 중 |
| 인증/보안 | Spring Security 커스텀 로그인, OAuth2, 이메일/전화 인증 |
| 외부 API | CoolSMS, Google SMTP, Kakao 주소 API, 기상청 초단기 API |
| 기타     | Jsoup 기반 HTML 크롤링 |

###  주요 기능

- 소셜 로그인(OAuth2), 이메일·전화 인증 통합
- 관리자 권한 분리 및 접근 제어 (@PreAuthorize)
- 게시글/댓글 본인 인증, 비로그인 차단
- 로그 자동 수집 및 30일 보존 스케줄링
- 구조적 보안 설계 + 외부 API 활용

### 주요 트러블 슈팅

- **트러블슈팅 1** :
     - 문제 : 로컬에서는 정상 동작하던 화면이 AWS EC2 배포 시 500 오류 발생
     - 원인 : Thymeleaf 템플릿 경로에서 layout 폴더를 참조할 때, 일부 템플릿에서는 layout, 일부는 Layout처럼 대소문자 혼용됨
     - 해결 : templates 디렉토리 내 폴더명과 참조 경로를 모두 소문자(layout)로 통일

- **트러블슈팅 2** :
     - 문제 : AWS 배포 시 일부 이미지가 정상적으로 출력되지 않음
     - 원인 : 프로젝트 이미지 파일들을 S3가 아닌 우분투 EC2 서버 내부로 직접 복사하여 사용했음, 이미지 확장자가 Png, PNG 등 대문자로 되어 있었는데, Linux 환경은 대소문자를 구분하므로 png로 작성된 경로와 일치하지 않아 오류 발생
     - 해결 : 이미지 파일 확장자 및 참조 경로를 모두 소문자(.png)로 통일


###  협업 및 회고

- Git 충돌 해결을 통해 협업의 구조적 중요성 체감
- 인증/보안 파트 전담 → 세션 인증 흐름 설계 경험
- Linux/AWS 기반 실전 감각 + 유지보수 중심 사고방식 추구
- aws 배포방법, readme 등 모든 내용 문서화 후 팀원에게 공유하였으나 다음엔 다른 인원이 직접 해보면 좋겠음

### 🔗 참고 문서

- [보안 설계 문서](https://github.com/yoon0416/ssgpack/blob/main/시큐리티.md)
- [트러블슈팅 문서](https://github.com/yoon0416/ssgpack/blob/main/트러블슈팅.md)
- [AWS 설정](https://github.com/yoon0416/ssgpack/blob/main/aws.md)
- [시연 영상](https://youtu.be/pWBEOX9JKqc)
- [문서 저장소](https://github.com/yoon0416/document)


---

##  경력 및 활동 요약

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

##  평가 가능한 장점 (Strengths)

- **상황 해결 중심**: 설계 레벨에서 문제 원인을 추적하고 구조로 대응  
- **보안 감수성**: 인증·공격 시나리오·테스트·침투 대응 경험  
- **문서화 역량**: README, 배포 가이드, 트러블슈팅 정리 습관  
- **시스템 구조 이해**: 팀 전체 흐름과 역할 파악에 강점  

---

##  Career Goals

- 설계에 기반한 기술 도입 및 구조적 확장 가능성 추구  
- Linux, SQL, AWS 기반으로 실용 중심 백엔드 성장  
- 보안 탐지 및 로그 설계 고도화 → 실전 대응 가능한 보안 시스템 구현  
- 다양한 인증/보안 도구를 커스터마이징할 수 있는 보안이 베이스인 백엔드 개발자 지향

