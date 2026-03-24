# 배종수
📞 01089358478 | ✉️ zephyrrr80@gmail.com

모놀리스에서 MSA로의 전환 설계, 대규모 트래픽 장애 대응, CI/CD 및 인프라 자동화 등 백엔드 서비스의 설계부터 운영까지 전 과정을 경험해 왔습니다.

요기요에서 트래픽 폭주 환경의 실시간 장애 대응과 성능 최적화를 경험했고, 혜움에서는 3개 MSA 신규 설계 및 SaaS 전환 아키텍처를 주도했습니다.

최근에는 Claude Code를 활용하여 백엔드에 국한되지 않고 서비스 전반의 개발 생산성을 높이는데 관심을 가지고 있습니다.

**경력 17년**

---

## 혜움

**2022.01 - 2026.03 (4년 3개월) | 정규직**

### AI 기반 개발 생산성 개선

- Claude Code 기반 AI 페어 프로그래밍 도입
- CLAUDE.md로 프로젝트 컨텍스트 및 코딩 규칙 관리
- 반복 작업을 Skills 로 정의하여 재사용
    - ex) 작업 완료 skill: lint 및 git commit 자동화
    - ex) TDD skill: best practice 기반으로 test 실패 → 수정 → test 성공 사이클 준수
- TDD 기반 개발 방식 적용
- plan - execute, 랄프루프, 에이전트팀 등 방법론 적용

### 메시징 시스템 구축

- 이메일 및 카카오 알림톡 통합 발송 시스템 구축
- 발송 이력 관리 및 실패한 알람 재발송 어드민 구축
- 결제 결과 알림, 비밀번호 찾기, 보안 알림 등 다양한 서비스 메시지 발송에 사용
- 대량 이메일 발송 기능 구현 및 운영 (최대 130만 발송, 4만 단위 배치 처리)
- SQS Worker 구조에서 발생한 DB Row Lock 문제 분석 및 해결

### RBAC 기반 구독 권한 시스템 재설계

- 구독 플랜 기반 기능 접근 제어를 위한 RBAC 권한 시스템 설계
- 회사 / 사용자 / 상품 / 롤 / 권한 구조 통합 관리
- 권한 체계를 메뉴 권한과 기능 권한으로 분리
- 메뉴 권한은 LNB 구성, 기능 권한은 메뉴 내 개별 기능 접근 제어에 활용

### 스크래핑 아키텍처 개선 및 장애대응

- Celery + redis lock 기반 스크래핑을 SQS FIFO + Lambda + S3 기반 이벤트 구조로 점진적 전환
- 신규 스크래핑 연동 기능에 신규 아키텍처 우선 적용
- 국내 IP 요구 금융사 대응을 위해 NCloud Proxy 기반 스크래핑 구조 운영
- Proxy 공개 이후 외부 접근 증가 문제를 분석하고 Lambda Private Subnet + NAT 기반 고정 IP 구조로 전환
- IP 차단 리스크를 고려하여 국내 IP 요구 금융사에만 고정 IP 선택 적용
- 스크래핑 현황을 Plotly 차트로 시각화하여 Slack 채널에 일일 리포트 자동 발송
- 스크래핑 규모 변동을 기반으로 이상 감지 알림 자동화

### 외부 파트너 SSO 연동 (유비케어)

- 외부 파트너 시스템에서 자사 서비스로의 SSO 진입 흐름 설계 및 구현
- API Key 기반 JWT 발급 및 인증 구조 설계
- 회사 정보를 포함한 JWT를 통해 사용자 진입 시 서비스 분기 처리 (가입 여부에 따른 처리)

### MSA 전환 및 SaaS 무료회원 서비스 오픈

- 기존 세무 고객 대상 모놀리스(SF) 구조를 MSA 아키텍처로 분리
- Django-Ninja 기반 cookiecutter 도입, MSA 표준 템플릿 구축
- Transaction MSA: 스크래핑 데이터 저장 및 조회 API 설계
- Remittance MSA: 매출/매입 현황 조회, 보고서, 세금 납부, 세금계산서 발급 등 비즈니스 기능 서비스
- Nexus MSA: 회원 / 회사 중앙 관리 및 JWT 인증 체계 구축
- 서비스 간 데이터 동기화 구조 설계 (Nexus → SF / Remittance / Transaction)

### 개발 환경 및 CI/CD 파이프라인 개선

- Terraform 기반 ECS + Fargate + ALB 인프라 구성
- GitHub Actions 기반 CI/CD 구축 (Staging / Production 자동 배포)
- Jira API + GitHub Actions + Fabric 연동으로 Release 브랜치 생성 및 배포 자동화
- AWS Secrets Manager 도입으로 민감정보 분리 및 설정 관리 개선
- 멀티 스테이징 환경 구축으로 동시 개발 및 테스트 병목 해소

---

## 위대한상상(요기요)

**2017.09 - 2021.12 (4년 4개월) | 정규직**

### Vendor Management Team Leader (2021.04 - 2021.12)

- 백엔드 개발팀 리드
- 코드 리뷰, 기술 의사결정, 팀원 멘토링 담당

### 대규모 주문 트래픽 대응 및 주문 시스템 안정화

- 일일 피크 타임(저녁 시간대) 주문 폭주에 대한 상시 장애 대응 및 안정화
- 주문 수 (Circuit Breaker) 기반 주문 제한 로직 운영
- 주문 수 계산을 디비 쿼리에서 redis incr/decr 기반 카운팅 방식으로 변경하여 DB 부하 감소
- 이벤트 대응을 위한 단계적 kill switch 운영 1~4단계

### 면접 문제은행 툴 제작 (2020.02 - 2020.03)

- 구글 시트로 관리하던 면접 문제를 체계적으로 관리할 수 있는 내부 툴 개발
- WebSocket을 통한 면접관 간 실시간 의견 공유 기능 구현
- 관련기술: Python, FastAPI, MongoDB, WebSocket, Vue.js, Nginx

### 신규 레스토랑 관리 시스템 (VMS) 개발 (2019.06 - 2021.07)

- 기존 레거시 레스토랑 관리 시스템을 대체하는 신규 프로젝트의 메인 개발자
- 운영자 인증 서버 역할을 겸하는 핵심 마이크로서비스로 설계
- AWS SNS/SQS를 활용한 기존 시스템과의 데이터 동기화 구현
- GitHub Actions, Fabric을 활용한 CI/CD 파이프라인 구축

### 파일 브라우저 개발 (2019.01 - 2019.04)

- 사내 운영자용 이미지 관리 툴 개발
- GCP Storage를 실제 저장소로 사용하고, AWS Serverless 아키텍처로 구성
- Chalice를 이용한 API 배포
- 관련기술: AWS Lambda, AWS API Gateway, AWS DynamoDB, AWS CloudSearch, AWS CloudFront, AWS S3, GCP Storage, Chalice

### 영업시간 관리 기능 개선 (2018.06 - 2018.12)

- 24시간 영업 매장의 영업시간 처리 버그 수정
- 일시중지, 반복설정, 연장오픈 등 신규 기능 개발
- Celery를 이용한 예약 삭제 작업 구현

### 기존 백엔드 유지보수 (2017.10 - 2021.12)

- Django 쿼리 최적화 다수 수행
- 캐시 오동작 케이스 분석 및 수정 (default key function 관련 이슈)
- Master-Slave DB 구조에서 Replication Lag으로 인한 get_or_create 오동작 해결 (Master 단일 조회로 변경)
- 주문 해지 프로세스 신규 개발

---

## 이전 경력

- **CDNetworks** (2012.12 - 2017.08) — CDN 운영 관리 시스템 및 고객 포털 개발 (Python, Django, AngularJS)
- **잉카인터넷** (2012.07 - 2012.11) — 보안 서비스용 가상키보드 개발 (JSP, JavaScript)
- **GCM Korea** (2011.04 - 2012.05) — 편의점 결제대행 서비스 개발 (Java, Spring)
- **Elamp** (2008.01 - 2010.11) — LMS(학습관리시스템) 개발 및 유지보수 (Java, Struts)

---

## 링크

- [GitHub](https://github.com/bae-jongsoo)
- [AI 주식 자동매매 프로그램](https://github.com/bae-jongsoo/alt-fast) | [링크](https://alt.jscraft.work)
  - 시장 데이터를 스크래핑하여 LLM에게 매수/매도 판단을 위임하는 자동매매 시스템 (FastAPI)
- [Django vs FastAPI 성능 벤치마크](https://github.com/bae-jongsoo/benchmark_apis)
  - CPU/IO/Mixed 워크로드별 동기 vs 비동기 처리 성능을 비교
- [테트리스 게임](https://github.com/bae-jongsoo/bj-tetris)
  - AI를 활용해 개발하고 Android까지 배포한 사이드 프로젝트

---

## 학력

**숭실대학교 | 컴퓨터학부 졸업**
