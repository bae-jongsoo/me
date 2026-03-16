# 이력서

## 소개
17년차 웹 서버 개발자입니다. 초기에는 풀스택 개발을 경험했고 이후 요기요에서 대규모 트래픽 환경을 경험하며 백엔드 개발자로 전환했습니다. 스타트업 환경에서 백엔드, 인프라, 아키텍처 설계까지 전반적인 플랫폼 개발을 담당해 왔습니다. 최근에는 Claude Code를 활용한 AI 페어 프로그래밍 방식으로 개발 생산성을 높이고 있습니다.

---

# 경력
총 경력: **17년 10개월**

## 혜움랩스 (2022.01 – 재직중)
Backend Developer / Platform Engineer

세무 서비스 플랫폼의 MSA 전환, SaaS 확장, 스크래핑 안정화, 권한 및 메시징 시스템 구축을 담당했습니다.

### 개발 환경 및 CI/CD 파이프라인 개선
- Terraform 기반 ECS + Fargate + ALB 인프라 구성
- GitHub Actions 기반 CI/CD 구축 (Staging / Production 자동 배포)
- Jira API + GitHub Actions + Fabric 연동으로 Release 브랜치 생성 및 배포 자동화
- AWS Secrets Manager 도입으로 민감정보 분리 및 설정 관리 개선
- 멀티 스테이징 환경 구축으로 동시 개발 및 테스트 병목 해소

### MSA 전환 및 SaaS 무료회원 서비스 오픈
- 기존 세무 고객 대상 모놀리스(SF) 구조를 MSA 아키텍처로 분리
- Django-Ninja 기반 MSA 표준 템플릿 구축
- Transaction MSA: 스크래핑 데이터 저장 및 조회 API 설계
- Remittance MSA: 세무 외 비즈니스 기능 서비스
- Nexus MSA: 회원 / 회사 중앙 관리 및 JWT 인증 체계 구축
- 서비스 간 데이터 동기화 구조 설계 (Nexus → SF / Remittance / Transaction)

### 스크래핑 장애 대응 및 모니터링
- 국내 IP 요구 금융사 대응을 위해 NCloud Proxy 기반 스크래핑 구조 운영
- Proxy 공개 이후 외부 접근 증가 문제를 분석하고 Lambda Private Subnet + NAT 기반 고정 IP 구조로 전환
- IP 차단 리스크를 고려하여 국내 IP 요구 금융사에만 고정 IP 선택 적용
- 스크래핑 현황을 Plotly 차트로 시각화하여 Slack 채널에 일일 리포트 자동 발송
- 스크래핑 규모 변동을 기반으로 이상 감지 알림 자동화

### 스크래핑 처리 아키텍처 개선
- Celery 기반 스크래핑을 SQS FIFO + Lambda + S3 기반 이벤트 구조로 점진적 전환
- 신규 스크래핑 연동 기능에 신규 아키텍처 우선 적용

### 스크래핑 에러 노말라이제이션 시스템 구축
- 금융기관별 비표준 에러 메시지 문제 해결을 위한 에러 정규화 시스템 설계
- 정규식 기반 에러 패턴 그룹화 및 관리
- 신규 에러 자동 수집 및 운영 대시보드 구축
- 재시도 가능 / 불가능 에러를 운영자가 관리하도록 개선

### RBAC 기반 구독 권한 시스템 재설계
- 구독 플랜 기반 기능 접근 제어를 위한 RBAC 권한 시스템 설계
- 회사 / 사용자 / 상품 권한 구조 통합 관리

### 메시징 시스템 구축 및 대량 이메일 장애 해결
- 이메일 및 카카오 알림톡 통합 발송 시스템 구축
- 결제 결과 알림, 비밀번호 찾기, 보안 이메일 등 다양한 메시지 발송 지원
- 130만 사용자 대상 대량 이메일 발송 기능 구현
- SQS Worker 구조에서 발생한 DB Row Lock Contention 문제 분석 및 해결

### AI 기반 개발 생산성 개선
- Claude Code 기반 AI 페어 프로그래밍 도입
- CLAUDE.md로 프로젝트 컨텍스트 및 코딩 규칙 관리
- 반복 작업을 Skills 파일로 정의하여 재사용
- TDD 기반 개발 방식 적용

## 요기요 (위대한상상) (2017.09 – 2021.12)
Backend Developer

### Vendor Management Team Leader (2021)
- 백엔드 개발팀 리드
- 코드 리뷰 및 기술 의사결정
- 팀원 멘토링

### 신규 레스토랑 관리 시스템(VMS) 개발
- 레거시 레스토랑 관리 시스템을 대체하는 신규 시스템 메인 개발
- 운영자 인증 서버 역할을 하는 핵심 마이크로서비스 설계
- AWS SNS / SQS 기반 기존 시스템과 데이터 동기화 구현
- GitHub Actions 기반 CI/CD 파이프라인 구축

### 대규모 트래픽 대응 및 주문 시스템 안정화
- 치킨 할인 이벤트 당시 저녁 시간대 트래픽 급증 대응
- 주문 수 제한(Circuit Breaker) 기반 주문 제한 로직 운영
- 주문 쓰로틀링 계산을 Request 기반 카운팅 방식으로 변경하여 DB 부하 감소
- 이벤트 대응을 위한 Kill Switch 운영 및 단계적 기능 비활성화 전략 적용

### 영업시간 관리 시스템 개선
- 해외 서비스 기준으로 설계된 영업시간 모델을 국내 서비스 환경에 맞게 개선
- 자정을 넘는 영업시간 및 복수 영업 구간 처리 문제 해결
- 영업시간 로직을 datetime range 기반 모델로 재설계

### 기존 백엔드 유지보수 및 성능 개선
- Django 쿼리 최적화
- 캐시 오동작 케이스 분석 및 수정
- Master-Slave Replication Lag으로 인한 get_or_create 오류 해결

### 내부 면접 문제은행 시스템 개발
- 면접 문제 관리 내부 웹 툴 개발
- WebSocket 기반 실시간 면접관 의견 공유 기능 구현

### 사내 파일 브라우저 개발
- 운영자용 이미지 관리 시스템 개발
- AWS Serverless 기반 API 설계

## CDNetworks (2012.12 – 2017.08)
Backend / Web Developer

- CDN 운영자 관리 시스템(OUI) 개발
- CDN 설정 관리 UI 및 고객 포털 기능 개발
- 레거시 포털 AngularJS + Django REST API 구조로 리팩토링

## Inca Internet (2012.07 – 2012.11)
- 보안 서비스용 가상키보드 개발 참여

## GCM Morea (2011.04 – 2012.05)
- 편의점 결제대행 서비스 개발

## Elamp (2008.01 – 2010.11)
- LMS(학습관리시스템) 개발 및 유지보수

## 기술 스택

**Language / Framework**  
Python, Django, Django-Ninja, DRF, FastAPI

**Infrastructure**  
AWS ECS, Fargate, Lambda, SQS, SNS, S3, ALB

**DevOps**  
Terraform, GitHub Actions, Fabric

**Database**  
PostgreSQL, MySQL, MongoDB

**Async / Messaging**  
Celery, Redis, AWS SQS

**Frontend**  
Vue.js, AngularJS

**AI Development**  
Claude Code
