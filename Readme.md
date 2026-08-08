<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css" />


## 과정개요

### NCS 등급의 이해 - https://www.ncs.go.kr/th01/TH-102-001-03.scdo
### 본 과정의 NCS 등급 - 5등급 - https://www.work24.go.kr/hr/a/a/3100/selectTracseDetl.do?tracseId=AIG20250000501686&tracseTme=6&cstmConsTme=&crseTracseSe=C0061&trainstCstmrId=500035988371&tracseReqstsCd=&focusId=


## 결론. 본 과정은 일반 NCS 2등급의 웹앱 개발자 수준보다 높은 수년차 이상의 경력인 5등급 과정으로
## 본인이 AI등의 각종 솔루션 도구를 이용하여 원하는 시스템을 구현하려는 과정 입니다. 
## 본 과정은 일반 프리젠테이션의 발표 스타일의 강의가 아닌 repo 단위의 실습을 실무에 적용하는 과정으로
## 철저하게 repo 단위로 실 사용 솔루션을 만드는 실습을 합니다. 
## 즉, 인문학 강의 같은 교안 만들고, ppt 설명, 펑션 실습, 퀴즈 등의 교습 절차 방식이 아닙니다. 

![alt text](images/readme-image-13.png)


## 이 과정의 3 분야

### 컴공 전공 또는 관련 분야 종사자 - 주식 투자의 기본 이해 및 개발을 위한 파트
### 금융 전공 또는 관련 분야 종사자 - Product Owner 로서 프로젝트 리드, IT 개발 기술 연습
### 기타 본인 지향 하는 바가 ML/DL 연구 분야 라면 - Python 및 ML/DL 등의 적용


---
---

# AI 에이전트의 도움을 어떻게 받을 것인가

## 플랫폼을 사용하는 방법 예시
## github 를 사용하는 방법을 예시로 설명 합니다. 내부 변수 지정

### repo 상단의 settings 메뉴 클릭
![alt text](images/readme-image.png)

### secrets and variables 메뉴 클릭
![alt text](images/readme-image-1.png)

### Actions 클릭
![alt text](images/readme-image-2.png)

### 변경화면에서 variables 메뉴클릭
![alt text](images/readme-image-3.png)

### New repo.. variable 버튼 클릭
![alt text](images/readme-image-4.png)

### 변수 입력 화면이 나옵니다.
![alt text](images/readme-image-5.png)

### 간단한 테스트 값 입력 후 버튼 클릭
![alt text](images/readme-image-6.png)


### 결과 화면
![alt text](images/readme-image-7.png)

### 지금 까지의 작업은 GH CLI 를 이용하지 않는 기존의 웹 콘솔 이용법 입니다.

## gh cli 이용 하기
### 본인 사용하는 에이전트 화면을 호출 합니다.
![alt text](images/readme-image-8.png)

### 프롬프트
- gh cli 설치 확인해줘
![alt text](images/readme-image-9.png)

- gh 로그인 확인해줘
![alt text](images/readme-image-10.png)

### 본인 repo , 위의 변수 입력 repo 를 명기하여 지시 합니다.
- https://github.com/edumgt/edumgt-lab-init 에 변수 test999/test999 입력해줘
![alt text](images/readme-image-11.png)

### 웹 콘솔에서 확인
![alt text](images/readme-image-12.png)


# edumgt 프로젝트 허브

![](images/infra.png)

> **edumgt** 교육 과정에서 운영되는 전체 프로젝트 목록과 상호 연관도입니다.
 
## AI 개발 환경 빠른 시작

VS Code에서 **Claude Code와 Codex를 설치·연동**하고 Docker Compose로 Ollama·Qdrant·PostgreSQL(pgvector) 등 AI/RAG 개발 컨테이너를 실행하는 최신 안내는 [AI 개발 환경 가이드](ai-dev-setup/README.md)를 참고하세요.

- Windows + WSL2, macOS, Linux별 Docker 설치·검증
- VS Code 필수 확장과 Claude Code/Codex 로그인·권한 설정
- `CLAUDE.md`, `AGENTS.md`를 이용한 프로젝트 규칙 분리
- Compose 프로필 기반 최소 AI/RAG, Graph RAG, 스트리밍, 모니터링 컨테이너 실행

---

# 작업물을 항상 git 또는 기타 산출물로 남기는 이유

# 제미나이(Gemini) 질의응답 시 IDC 센터 물리적 비용 분석

사용자가 제미나이(Gemini) 같은 거대 언어 모델(LLM)에 질문을 던지고 답변을 받을 때, 구글의 IDC(데이터 센터) 내부에서 **물리적(인프라적)으로 발생하는 비용**은 크게 4가지 축으로 나뉩니다.

단순히 소프트웨어 코드가 도는 것이 아니라, 전력과 하드웨어 감가상각비가 실시간으로 소모되는 과정입니다. 질문 1회(1 Query, 약 1,000~2,000토큰 처리 기준)당 발생하는 물리적 비용의 구조는 다음과 같습니다.

---

## 1. 하드웨어 감가상각 및 컴퓨팅 비용 (가장 큰 비중)
제미나이는 구글이 자체 개발한 AI 반도체인 **TPU(Tensor Processing Unit)** 또는 엔비디아의 GPU 칩 수천~수만 개가 연결된 서버 랙에서 구동됩니다.
* **실제 비용:** 질문을 처리하기 위해 수십 대의 TPU/GPU가 몇 초 동안 100%에 가까운 연산력을 집중해야 합니다.
* **감가상각:** 칩 하나당 수천만 원에 달하고 수명이 3~5년에 불과하기 때문에, 질문을 처리하는 초 단위의 시간 동안 칩의 수명과 가치가 깎이는 '장비 감가상각비'가 물리적 비용의 핵심입니다.

## 2. 전력 소비 비용 (전기세)
AI 모델은 엄청난 전기를 먹는 '하마'입니다.
* **연산 전력:** 질문 하나를 던지면 서버가 이를 해석하고(인프런스), 다음 단어를 예측해 문장을 생성하는 과정에서 엄청난 전류가 흐릅니다.
* **소모량:** 일반적인 복잡한 LLM 질문 1회당 대략 **0.01~0.03kWh(킬로와트시)** 안팎의 전력이 소모되는 것으로 추정됩니다. 이는 스마트폰을 몇 시간 동안 충전하거나, LED 전등을 한참 켜둘 수 있는 양입니다.

## 3. 냉각(Cooling) 및 수자원 비용
서버가 전기를 쓰면 그만큼 엄청난 열이 발생합니다. 이 열을 식히지 않으면 서버가 타버리기 때문에 IDC는 24시간 냉각 시스템을 돌려야 합니다.
* **공조 전력:** 서버가 쓰는 전력만큼(혹은 그 이상) 냉각용 에어컨과 냉각수 펌프를 돌리는 데 물리적 전력이 추가로 듭니다. (이를 PUE 지표로 계산합니다.)
* **수자원 증발:** 냉각탑을 돌리며 엄청난 양의 물이 증발합니다. 대형 AI 모델에 질문을 10~50개 던질 때마다 약 **500ml 생수 한 병 분량의 물**이 냉각을 위해 소비(증발)된다는 연구 결과가 있습니다.

## 4. 네트워크 및 대역폭 비용
사용자가 입력한 텍스트가 구글 IDC로 들어오고, 생성된 결과물이 전 세계 해저 광케이블과 네트워크 망을 거쳐 사용자의 화면에 뿌려지는 물리적 데이터 전송 비용입니다. (다만 데이터 크기 자체는 텍스트 위주라 컴퓨팅/냉각 비용에 비하면 비중이 작습니다.)

---

### 💡 요약하자면: 질문 1번의 '진짜 물리적 비용'은?

업계 분석에 따르면, 제미나이나 GPT 같은 대형 모델에 **복잡한 질문을 1번 던질 때 구글이 부담하는 순수 물리적 운영/인프라 비용(Marginal Compute Cost)은 약 0.01달러 ~ 0.03달러(한화 약 13원 ~ 40원)** 수준으로 추정됩니다.

> 만약 추론(Reasoning) 프로세스가 포함된 매우 무거운 질문이라면, 한 번 대답할 때마다 인프라 비용만 **0.1달러 ~ 0.5달러(약 130원 ~ 650원)**까지 치솟기도 합니다. 사용자가 무료로 쓰거나 월 20달러 구독료를 내더라도, 헤비 유저가 질문을 쏟아내면 구글 입장에서는 물리적 적자가 발생하는 구조가 바로 이 때문입니다.

---

## 프로젝트 목록 (공개 저장소 55개 · https://github.com/edumgt 기준, 2026-07-03)

### <i class="fa-solid fa-cube"></i> 1단계 — 개발환경 & 기초

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **edumgt-lab-init** | 개발환경 최초 설정 가이드. WSL2·Python·Node·Java·Docker·K8s 순차 실습 | WSL2, Python, Node.js, Java, Docker, K8s |
| **python-basic-lab** | 파이썬 기초 + 실전 자동화 실습을 함께 다루는 학습형 저장소 | Python, 자동화 스크립트 |
| **java-lab** | Java 초급 입문 | Java, 전자정부 표준프레임워크 |
| **py-util** | DART·KOSIS 등 공공/기업 데이터 수집 크롤링 유틸리티 스크립트 모음 | Python, requests, DART API |

---

### <i class="fa-brands fa-docker"></i> 2단계 — 인프라, 컨테이너 & 클라우드

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **docker-class** | Docker 기초~심화 Lab + Jenkins·GitLab·SonarQube·Nexus·Drone 온프레미스 DevSecOps | Docker, Jenkins, GitLab CE, SonarQube, Nexus |
| **harbor-lab** | 온프레미스 Docker 이미지 레지스트리 Harbor 구축 실습 | Docker, Harbor |
| **keycloak-lab** | Keycloak 기반 OAuth2/OIDC 인증·인가 실습 | Docker, Keycloak, OAuth2 |
| **kubernetes-lab** | K8s 아키텍처 → 배포 → 오토스케일링 → 트러블슈팅 단계별 실습 | kubeadm, kubectl, HPA, Ingress |
| **k8s-jupyter-lab** | K8s 기반 사용자별 JupyterLab 세션 + Harbor 스냅샷 복원 + 오프라인 OVA | kubeadm, JupyterLab, Harbor, MetalLB |
| **vmware-k8s-jupyter** | VMware 기반 On-Prem K8s 샌드박스 클래스 | VMware, kubeadm, JupyterLab |
| **msa-k8s-lab** | Kubernetes 기반 MSA(마이크로서비스) 배포 테스트 | Java, Kubernetes, MSA |
| **springboot-lab** | Spring Cloud Gateway + 8개 마이크로서비스, PostgreSQL/Redis/Kafka 인프라 | Spring Boot, Spring Cloud Gateway, Kafka, Redis |
| **openstack-private-cloud** | Ansible 기반 OpenStack 프라이빗 클라우드 구축 (Keystone/Nova/Neutron/Cinder) | Ansible, OpenStack, Ubuntu |
| **azure-aws-openstack** | Azure·AWS·OpenStack 클라우드 아키텍처 비교/정리 | Azure, AWS, OpenStack |
| **aws-ec2-alb-lab** | EC2/VPC/ALB → Auto Scaling → ECS Fargate 배포까지의 고가용성 아키텍처 Lab | AWS EC2, ALB, ECS Fargate, FastAPI |
| **aws-serverless** | AWS Lambda + API Gateway 서버리스 실습 (Node.js·Python·Java) | AWS Lambda, API Gateway |
| **aws-eks-lab** | AWS EKS 클러스터 구성 → ECR → ALB Ingress → 오토스케일링 실전 운영 | AWS EKS, eksctl, ECR, ALB Ingress |
| **aws-polly** | Amazon Polly TTS 실습 — FastAPI + S3 Presigned URL + Lambda 서버리스 | Amazon Polly, S3, Lambda |
| **aws-rekognition** | AWS Rekognition 얼굴·텍스트 인식 실습 + Custom Labels 도메인 튜닝 | AWS Rekognition, Lambda, S3 |
| **aws-sqs-sns** | AWS SQS·SNS 메시지 큐/알림 + ElastiCache Cache-Aside 실습 | AWS SQS, SNS, ElastiCache |
| **aws-transcribe** | Amazon Transcribe 음성→텍스트 실습 + SRT/VTT 자막 변환 | AWS Transcribe, Node.js AWS SDK v3 |
| **chatbot-app** | 모의 증권사 투자상담 챗봇 데모 — Vue/Quasar + AWS Lex/Cognito, AWS-free FastAPI 버전 포함 | Amazon Lex V2, Cognito, Vue, FastAPI |

---

### <i class="fa-solid fa-chart-bar"></i> 3단계 — 데이터 수집 & 파이프라인

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **python-crawling-lab** | 정적·동적 페이지 데이터 수집 및 자동화 크롤링 실습 | Python, BeautifulSoup, Selenium, Qdrant |
| **multi-db-lab** | AG Grid 기반 멀티 데이터베이스 CRUD 실습 | Python, AG Grid, RDB |
| **pipeline-lab** | AI 기반 사내 데이터 파이프라인 구성 | Python, ETL/Pipeline |

---

### <i class="fa-solid fa-robot"></i> 4단계 — 머신러닝, 딥러닝 & 컴퓨터비전

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **python-ml-class** | 머신러닝 기초 → Transformer 주가 방향 분류 모델 구현 | scikit-learn, PyTorch, Transformer, yfinance |
| **stock-ml-dl-project** | 시계열 데이터 분석 기반 주가 예측 ML/DL 파이프라인 | scikit-learn, TensorFlow/PyTorch, 시계열 |
| **yolo-lab** | 인증 기반 업로드 → YOLO 분석 → 결과 상태 조회를 지원하는 컴퓨터비전 프로젝트 | Flask, YOLO, OpenCV |
| **huggingface-lab** | Stable Diffusion 이미지/영상 생성 + yfinance 주식 분석 차트 웹 스튜디오 | HuggingFace, Stable Diffusion, yfinance |
| **composer-ai-agent** | 머신러닝 기반 MP3 자동 작곡 에이전트 | Python, ML, 오디오 생성 |
| **matlab-class** | MATLAB 연동 데이터 대시보드 | TypeScript, MATLAB |

---

### <i class="fa-solid fa-feather"></i> 5단계 — LLM, RAG & AI Agent

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **langchain-lab** | LangChain 기능 카탈로그(기능별 독립 데모) — LCEL·RAG·Agent, Ollama/OpenAI 스위칭 | LangChain, Ollama, OpenAI, Qdrant |
| **flowise-lab** | Flowise + LangChain JS + LlamaIndex Py + 에어갭(폐쇄망) 시뮬레이션 | Flowise, LangChain.js, LlamaIndex |
| **ai-agent-lab** | Python AI Agent 종합 커리큘럼 — 전처리/시각화 → ML/DL → NLP/음성 → 에이전트, LLMOps | Python, LangChain, HuggingFace, Qdrant |
| **aihub-rag** | AI Hub 등 한국어 공공데이터를 JSONL로 정규화한 도메인 특화 RAG (의료·법률·심리상담·여행·금융) | FastAPI, Qdrant, HuggingFace, Docker |
| **domain-rag-lab** | 의학·고교영어 도메인 특화 AI Agent RAG | Python, RAG, Domain Agent |
| **education-counsel** | 학생 진로상담 데이터를 검색·생성형 AI로 연결한 RAG 웹서비스 | FastAPI, Qdrant, MongoDB, Azure |
| **ollama-llava-canvas** | Ollama LLaVA 기반 캔버스 드로잉 + AI 이미지 향상 | Ollama, LLaVA, FastAPI, HTML5 Canvas |
| **meeting-agent** | 회의 녹음 → STT 전사 → 회의록 리포트 자동 생성 웹 앱 | FastAPI, OpenAI Whisper, ffmpeg |
| **whisper-agent** | 상담 데이터 수집/분석 + 벡터 검색 기반 RAG 리포트 생성 | FastAPI, ChromaDB, OpenAI, Ollama |
| **ocr-webapp** | Tesseract OCR + AI 보완 웹앱 (Nginx + FastAPI + 관리자 대시보드) | FastAPI, Tesseract 5, Nginx, Ollama |
| **vdp-agent** | AI Agent 기반 VDP(차량/문서) PDF 자동 생성 모듈 | Node.js, PDF 생성, AI Agent |
| **ultrasound-report** | 의료 초음파 판독 리포트 자동화 웹앱 | Python, Django |
| **fortune-ai-agent** | AI 기반 만세력·사주·운세풀이·MBTI·투자성향 분석 서비스 | JavaScript, LLM Agent |

---

### <i class="fa-solid fa-chart-line"></i> 6단계 — 금융 & 투자 실전 프로젝트

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **investment-analysis** | 금융투자 지식을 실전 서빙 시스템으로 — FastAPI 퀀트/ML/DL API, DART 공시 연동, RAG 지식 문서 축적 | FastAPI, Qdrant, DART API |
| **python-ai-basic-lab** | 퀀트를 위한 Python AI/ML 12일 실습 — FastAPI 주식 AI 실험실(ML/DL 비교) + Ollama 해설 | FastAPI, Plotly, yfinance, Ollama |
| **stock-coin-trade** | 한국 4대 코인거래소 시세 + Spring Boot 코인·주식 통합 모의투자 웹앱 | Spring Boot, Thymeleaf, PostgreSQL |
| **lumina-invest** | Python FastAPI 금융 AI 에이전트 — ReAct 챗봇, 퀀트 자동매매(LightGBM/MLP 백테스트), Qdrant RAG | FastAPI, Neo4j, Qdrant, LightGBM |
| **invest-flow** | AI 기반 개인 투자 일정관리 앱 — 포트폴리오 추적 + 매수/매도/리밸런싱 캘린더 | Vue 3, FastAPI, PostgreSQL, Claude AI |
| **voice-analyzer** | 국내외 금융/투자 사이트 크롤링 → AI(OpenAI/Ollama/Upstage Solar) 시장 분석 → 한국어 TTS 요약 | 크롤링, LLM, TTS |

---

### <i class="fa-solid fa-layer-group"></i> 7단계 — 풀스택 응용 서비스

| 저장소 | 설명 | 핵심 기술 |
|--------|------|-----------|
| **fe-vanilla** | AI 시대의 Vanilla JS/HTML 프론트엔드 기초 | JavaScript, HTML/CSS |
| **webrtc-app** | 실시간 화상·채팅·파일·화이트보드 협업 WebRTC 애플리케이션 | Vue, WebRTC |
| **inquiry-saas** | 해외 파트너사가 한국 도착 수입 화물의 내륙 운송비를 실시간 조회·견적 발행하는 B2B SaaS | JavaScript, Node.js, SaaS |

---

### <i class="fa-solid fa-id-card"></i> 메타 저장소

| 저장소 | 설명 |
|--------|------|
| **edumgt** | GitHub 프로필 소개 저장소 |
| **.github** | 조직 공통 커뮤니티 파일(이슈/PR 템플릿 등) |
## 프로젝트 연관도 (단계별 흐름)

```
┌───────────────────────────────────────────────────────────────────┐
│ 1단계: 개발환경 & 기초                                              │
│  edumgt-lab-init (WSL2·Python·Node·Java·Docker·K8s 환경 구축)      │
│       ├─→ python-basic-lab   ├─→ java-lab   └─→ py-util           │
└───────────────────────┬───────────────────────────────────────────┘
                         ▼
┌───────────────────────────────────────────────────────────────────┐
│ 2단계: 인프라, 컨테이너 & 클라우드                                   │
│                                                                     │
│  docker-class ──→ harbor-lab / keycloak-lab (레지스트리·인증)      │
│       │                                                             │
│       ├─→ kubernetes-lab ──→ k8s-jupyter-lab / vmware-k8s-jupyter  │
│       │        └─→ msa-k8s-lab ──→ springboot-lab                 │
│       │                                                             │
│       ├─→ openstack-private-cloud / azure-aws-openstack           │
│       │                                                             │
│       └─→ AWS 트랙: aws-ec2-alb-lab → aws-eks-lab                 │
│           aws-serverless, aws-polly, aws-rekognition,              │
│           aws-sqs-sns, aws-transcribe, chatbot-app                 │
└───────────────────────┬───────────────────────────────────────────┘
                         ▼
┌───────────────────────────────────────────────────────────────────┐
│ 3단계: 데이터 수집 & 파이프라인                                      │
│  python-crawling-lab / multi-db-lab / pipeline-lab                 │
└───────────────────────┬───────────────────────────────────────────┘
                         ▼
┌───────────────────────────────────────────────────────────────────┐
│ 4단계: 머신러닝, 딥러닝 & 컴퓨터비전                                  │
│  python-ml-class ──→ stock-ml-dl-project                           │
│  yolo-lab · huggingface-lab · composer-ai-agent · matlab-class     │
└───────────────────────┬───────────────────────────────────────────┘
                         ▼
┌───────────────────────────────────────────────────────────────────┐
│ 5단계: LLM, RAG & AI Agent                                          │
│  langchain-lab / flowise-lab ──→ ai-agent-lab                      │
│       │                                                             │
│       ├─→ aihub-rag ──→ domain-rag-lab ──→ education-counsel      │
│       ├─→ ollama-llava-canvas                                      │
│       ├─→ meeting-agent / whisper-agent / ocr-webapp               │
│       └─→ vdp-agent / ultrasound-report / fortune-ai-agent         │
└───────────────────────┬───────────────────────────────────────────┘
                         ▼
┌───────────────────────────────────────────────────────────────────┐
│ 6단계: 금융 & 투자 실전 프로젝트                                     │
│  investment-analysis ──→ python-ai-basic-lab                       │
│       ├─→ lumina-invest (Neo4j + ReAct + 퀀트 자동매매)            │
│       ├─→ invest-flow (Vue3 + Claude AI 투자 캘린더)               │
│       ├─→ stock-coin-trade (Spring Boot 모의투자)                  │
│       └─→ voice-analyzer (크롤링 + LLM + TTS 시장 브리핑)          │
└───────────────────────┬───────────────────────────────────────────┘
                         ▼
┌───────────────────────────────────────────────────────────────────┐
│ 7단계: 풀스택 응용 서비스                                            │
│  fe-vanilla · webrtc-app · inquiry-saas                             │
└───────────────────────────────────────────────────────────────────┘
```

---

## 학습 경로 (권장 순서)

### 경로 A — 백엔드/풀스택 개발자
```
edumgt-lab-init → python-basic-lab / java-lab → docker-class
  → kubernetes-lab → springboot-lab / msa-k8s-lab
  → langchain-lab → education-counsel
  → fe-vanilla / webrtc-app / inquiry-saas (서비스 개발)
```

### 경로 B — MLOps/데이터 엔지니어
```
edumgt-lab-init → python-basic-lab → python-crawling-lab / pipeline-lab
  → python-ml-class → stock-ml-dl-project
  → docker-class → kubernetes-lab → k8s-jupyter-lab
  → ai-agent-lab
```

### 경로 C — AI/LLM 엔지니어
```
edumgt-lab-init → python-basic-lab → python-crawling-lab (Qdrant 연동)
  → langchain-lab / flowise-lab → aihub-rag → domain-rag-lab
  → ai-agent-lab → meeting-agent 또는 whisper-agent
```

### 경로 D — 클라우드/인프라 엔지니어
```
edumgt-lab-init → docker-class → harbor-lab → keycloak-lab
  → kubernetes-lab → k8s-jupyter-lab / vmware-k8s-jupyter
  → openstack-private-cloud → azure-aws-openstack
  → aws-ec2-alb-lab → aws-eks-lab
  → (aws-polly, aws-rekognition, aws-sqs-sns, aws-transcribe)
```

### 경로 E — 핀테크/금융 AI
```
edumgt-lab-init → python-basic-lab → python-crawling-lab
  → python-ml-class → python-ai-basic-lab → investment-analysis
  → stock-ml-dl-project → lumina-invest / invest-flow / stock-coin-trade / voice-analyzer
```

### 경로 F — 도메인 특화 AI 서비스(의료·교육·컴퓨터비전)
```
edumgt-lab-init → python-basic-lab → huggingface-lab / yolo-lab
  → langchain-lab → aihub-rag → domain-rag-lab
  → ultrasound-report / education-counsel / fortune-ai-agent
```

---

## 명시적 선후 관계

| 프로젝트 | 선수 프로젝트 | 근거 |
|----------|--------------|------|
| kubernetes-lab | docker-class | K8s 실습 전 Docker 컨테이너 이해 필수 |
| k8s-jupyter-lab / vmware-k8s-jupyter | kubernetes-lab | K8s 기반 플랫폼 배포 경험 필요 |
| harbor-lab / keycloak-lab | docker-class | Docker 컨테이너·레지스트리 개념 선행 |
| msa-k8s-lab | kubernetes-lab | K8s 위에서 MSA 배포 실습 |
| springboot-lab | msa-k8s-lab | 마이크로서비스 아키텍처 이해 후 Gateway 구성 |
| aws-eks-lab | aws-ec2-alb-lab | AWS 네트워크·IAM 구성 경험 후 EKS |
| openstack-private-cloud | docker-class | Ansible 실습 환경에 Docker 사용 |
| aws-ec2-alb-lab | docker-class | ECS Fargate = 컨테이너 기반 |
| domain-rag-lab / aihub-rag | python-crawling-lab | 데이터 정규화·Qdrant 구조 이해 필요 |
| education-counsel | aihub-rag / domain-rag-lab | RAG 응용 패턴 이해 후 진행 |
| stock-ml-dl-project | python-ml-class + kubernetes-lab | ML 모델 + K8s 배포 병행 |
| ai-agent-lab | langchain-lab | LangChain Agent 기반 커리큘럼 |
| invest-flow / lumina-invest | investment-analysis | 금융 도메인 지식 기반 앱 |
| voice-analyzer | python-crawling-lab | 크롤링 파이프라인 재사용 |

---

## 기술 스택 분포

| 레이어 | 기술 | 관련 프로젝트 수 |
|--------|------|-----------------|
| **프레임워크** | FastAPI | aws-ec2-alb-lab, aihub-rag, education-counsel, investment-analysis, lumina-invest, ollama-llava-canvas, python-ai-basic-lab, aws-polly, meeting-agent, whisper-agent, ocr-webapp, chatbot-app, invest-flow (13개) |
| **프레임워크** | Spring Boot | stock-coin-trade, springboot-lab (2개) |
| **AI/LLM** | LangChain | langchain-lab, flowise-lab, ai-agent-lab (3개) |
| **AI/LLM** | Ollama | langchain-lab, ollama-llava-canvas, whisper-agent, ocr-webapp, python-ai-basic-lab, voice-analyzer (6개) |
| **AI/LLM** | OpenAI Whisper/GPT | meeting-agent, whisper-agent, voice-analyzer (3개) |
| **Vector DB** | Qdrant | python-crawling-lab, aihub-rag, education-counsel, investment-analysis, ai-agent-lab, langchain-lab, lumina-invest (7개) |
| **Vector DB** | ChromaDB | whisper-agent (1개) |
| **Graph DB** | Neo4j | lumina-invest (1개) |
| **컨테이너/오케스트레이션** | Docker / Kubernetes | docker-class, harbor-lab, keycloak-lab, kubernetes-lab, k8s-jupyter-lab, vmware-k8s-jupyter, msa-k8s-lab (7개) |
| **클라우드** | AWS | aws-serverless, aws-ec2-alb-lab, aws-eks-lab, aws-polly, aws-rekognition, aws-sqs-sns, aws-transcribe, chatbot-app (8개) |
| **프라이빗 클라우드** | OpenStack | openstack-private-cloud, azure-aws-openstack (2개) |
| **스트리밍/큐** | Kafka / SQS / SNS | springboot-lab, aws-sqs-sns (2개) |
| **컴퓨터비전** | YOLO / Stable Diffusion / OCR | yolo-lab, huggingface-lab, ocr-webapp (3개) |
| **프론트엔드** | Vue 3 | invest-flow, webrtc-app, chatbot-app (3개) |
| **프론트엔드** | Vanilla JS/HTML | fe-vanilla, ollama-llava-canvas, stock-coin-trade (3개) |

---

# 🚀 소형 언어 모델(sLLM) 및 서빙 엔진(vLLM, Ollama) 완벽 정리

## 1. 핵심 3가지 개념 요약

| 기술 | 핵심 개념 | 역할 (비유) | 주요 용도 |
| :--- | :--- | :--- | :--- |
| **sLLM** | 소형 거대 언어 모델 | 연비가 좋은 맞춤형 **'자동차'** (데이터 자체) | 비용 절감, 사내 보안(온프레미스), 특정 도메인 특화 |
| **Ollama** | 로컬 실행 도구 | 다루기 쉬운 개인용 **'차고/플레이어'** | 개인 PC 개발용, 가벼운 로컬 테스트, 프로토타입 |
| **vLLM** | 고성능 서빙 엔진 | 막힘없이 달리는 초고속 **'하이웨이'** | 대규모 사용자가 몰리는 실제 기업 웹 서비스 배포 |

---

## 2. 개념별 상세 설명

### 💡 sLLM (Small Large Language Model)
* **정의:** GPT-4 같은 초대형 LLM의 덩치(매개변수)를 수십억~수백억 개(7B, 13B 등) 수준으로 다이어트시킨 모델입니다.
* **특징 및 장점:**
    * **가성비:** 하드웨어 사양을 낮출 수 있어 GPU 서버 운영 비용이 대폭 감소합니다.
    * **보안성:** 모델 크기가 작아 외부 클라우드를 쓰지 않고 기업 내부 서버(On-Premise)에 직접 구축할 수 있습니다.
    * **특화 성능:** 특정 산업군(금융, 법률, 의료 등)의 데이터로 파인튜닝하면, 특정 영역에서는 거대 모델 못지않은 성능을 냅니다.
* **대표 예시:** Llama 3, Gemma, Mistral, DeepSeek-R1-Distill 등

### 💡 Ollama
* **정의:** sLLM 모델을 개인 PC(Mac, Windows, Linux) 환경에서 명령어 한 줄로 다운로드하고 실행할 수 있게 해주는 애플리케이션입니다.
* **특징 및 장점:**
    * **편의성:** `ollama run llama3` 명령어 하나면 모델 다운로드부터 API 서버 구동까지 끝납니다.
    * **개발 생산성:** 로컬 개발 환경에서 빠르게 테스트 버전을 만들거나 프롬프트 엔지니어링을 실험할 때 최적입니다.

### 💡 vLLM
* **정의:** LLM/sLLM을 실제 웹 서비스 환경에서 사용할 때, 추론(답변 생성) 속도를 극한으로 끌어올려 주는 오픈소스 서빙 프레임워크입니다.
* **특징 및 장점:**
    * **PagedAttention 기술:** 운영체제(OS)의 가상 메모리 개념을 도입하여, 답변 생성 시 발생하는 메모리(KV 캐시) 낭비를 0% 가깝게 줄입니다.
    * **고처리량(High Throughput):** 동일한 GPU 장비에서 기존 방식 대비 **2~4배 이상의 동시 요청**을 처리할 수 있어 서버 비용이 획기적으로 절감됩니다.

---

## 3. 역할별 유사 기술 스택 (Alternative Tech Stack)



### ① Ollama의 대체재 (개인/개발용 도구)
* **llama.cpp:** Ollama의 핵심 구동 엔진이기도 한 원조 오픈소스입니다. C/C++로 작성되어 가벼우며, GPU가 없는 환경이나 맥북(Apple Silicon)에서 뛰어난 성능을 냅니다.
* **LM Studio:** 터미널 명령어가 아닌 깔끔한 그래픽 UI(GUI)를 제공하는 프로그램입니다. 마우스 클릭만으로 Hugging Face의 다양한 sLLM 모델을 받아 챗GPT처럼 테스트할 수 있습니다. OpenAI 호환 로컬 API 서버도 내장되어 있어 기존 코드를 수정 없이 로컬 모델로 전환할 수 있습니다.

  > **📘 LM Studio 설치·사용 가이드:** [lmstudio/README.md](lmstudio/README.md) — 다운로드, 모델 설치, 채팅, API 서버, Python/Node.js 연동 예제 포함

### ② vLLM의 대체재 (실전 웹 서비스/프로덕션용 엔진)
* **SGLang:** 최근 벤치마크에서 vLLM을 능가하며 급부상한 고성능 엔진입니다. 복잡한 AI 에이전트 워크플로우나 구조화된 데이터(JSON) 출력을 처리할 때 vLLM보다 더 빠르고 효율적입니다.
* **NVIDIA TensorRT-LLM:** 엔비디아가 자사 GPU 성능을 한계까지 쥐어짜기 위해 만든 공식 최적화 라이브러리입니다. 설정이 까다롭지만, 단일 GPU당 처리량 성능은 가장 압도적입니다.
* **Hugging Face TGI (Text Generation Inference):** 허깅페이스에서 개발한 전통적인 강자 서빙 엔진으로, 대규모 배포 환경에서 안정적인 운영을 지원합니다.

---

## 4. 실무 인프라 구성 가이드 (Best Practice)

### 🛠️ 조합 A: 로컬 및 프로토타입 개발 환경 (가장 쉽고 빠름)
* **구성:** `Docker` ➡️ `Ollama 컨테이너` ➡️ `sLLM(Llama 3 등) 구동`
* **설명:** 개인 노트북이나 테스트 서버에서 sLLM 기반 앱을 빠르게 프로토타이핑할 때 가장 권장되는 구성입니다.

### 🏭 조합 B: 실제 대고객 서비스 배포 환경 (성능 극대화)
* **구성:** `Docker` ➡️ `vLLM (또는 SGLang) 컨테이너` ➡️ `Hugging Face 등에서 sLLM 모델 로드`
* **설명:** 동시 접속자가 많은 상용 서비스 환경에서 GPU 메모리를 낭비 없이 완벽하게 활용하여 응답 지연을 최소화하는 엔터프라이즈급 구성입니다.

---


## 수강생 사전 준비 및 회차별 체크리스트

### 수강생 입장 준비 워크플로우

```mermaid
flowchart TD
    A((수강 준비 시작)) --> B{GitHub 계정 있음?}
    B -->|없음| C[github.com 회원가입\n2FA 활성화]
    B -->|있음| D[저장소 Fork 또는 Clone]
    C --> D
    D --> E[본인 PC 환경 점검\nNode.js / Python / Git 설치 확인]
    E --> F{AI 플랫폼 계정 준비}
    F --> G[ChatGPT / Claude / Gemini\n각 계정 생성 및 로그인 확인]
    G --> H[수업 전날 밤\n해당 회차 목표 README 읽기]
    H --> I[당일 수업 시작]
    I --> J[AI 플랫폼 접속 확인]
    J --> K{접속 불가?}
    K -->|예| L[대체 플랫폼으로 전환\nChatGPT → Claude → Gemini 순]
    K -->|아니오| M[실습 진행\n프롬프트 작성 및 결과 비교]
    L --> M
    M --> N[실습 결과를 .md 파일로 정리]
    N --> O[git add → git commit → git push]
    O --> P{PR 제출 필요?}
    P -->|예| Q[GitHub Pull Request 생성]
    P -->|아니오| R((회차 완료))
    Q --> R
```

### 수강 전 1회성 환경 구성 체크리스트

> 과정 시작 전 아래 항목을 모두 완료해야 실습에 원활하게 참여할 수 있습니다.

#### GitHub / Git 환경

- [ ] GitHub 계정 생성 (https://github.com)
- [ ] 2단계 인증(2FA) 활성화 — Settings → Password and authentication
- [ ] 과정 저장소 Fork 또는 Clone 완료
  ```bash
  git clone https://github.com/edumgt/edumgt-lab-init.git
  cd edumgt-lab-init
  ```
- [ ] Git 사용자 정보 설정
  ```bash
  git config --global user.name "본인 이름"
  git config --global user.email "본인 이메일"
  ```
- [ ] 첫 커밋 테스트 — 본인 소개 `.md` 파일 작성 후 push 성공 확인

#### AI 플랫폼 계정 (3개 필수 + 선택)

| 플랫폼 | URL | 필수 여부 | 확인 |
|--------|-----|----------|------|
| ChatGPT | https://chatgpt.com | 필수 | [ ] |
| Claude | https://claude.ai | 필수 | [ ] |
| Gemini | https://gemini.google.com | 필수 | [ ] |
| Perplexity | https://www.perplexity.ai | 권장 | [ ] |
| Grok | https://grok.com | 선택 | [ ] |
| NotebookLM | https://notebooklm.google.com | 권장 | [ ] |

#### 개발 도구

- [ ] VS Code 설치 (https://code.visualstudio.com)
  - [ ] Markdown Preview Enhanced 확장 설치
  - [ ] GitHub Copilot 확장 설치 (선택)
- [ ] Python 3.11+ 설치 확인: `python --version`
- [ ] Node.js 20 LTS 설치 확인: `node --version`
- [ ] Docker Desktop 설치 확인: `docker --version`
- [ ] Ollama 설치 (4회차 로컬 AI 실습용, 권장)
  ```bash
  curl -fsSL https://ollama.com/install.sh | sh
  ollama pull llama3.2:3b   # 경량 모델 사전 다운로드
  ```
- [ ] LM Studio 설치 (GUI 방식 로컬 AI, 선택 — CLI 대신 마우스로 모델 관리 가능)
  - 다운로드: https://lmstudio.ai
  - 설치 가이드: [lmstudio/README.md](lmstudio/README.md)
  - 권장 모델: `Qwen2.5 7B Instruct Q4_K_M` 또는 `Llama 3.2 3B Q4_K_M`

---


### Playwright 자동 캡처 (권장)

Playwright로 브라우저를 자동 제어해 AI 결과 화면을 캡처합니다.

```bash
# Playwright 설치
pip install playwright
playwright install chromium
```

```python
# capture_result.py — AI 플랫폼 화면 자동 캡처 스크립트
from playwright.sync_api import sync_playwright
from datetime import date
import os

DATE = date.today().isoformat()           # 예: 2025-07-13
SAVE_DIR = f"assignments/{DATE}/screenshots"
os.makedirs(SAVE_DIR, exist_ok=True)

def capture(url: str, filename: str, wait_ms: int = 3000):
    with sync_playwright() as p:
        browser = p.chromium.launch(headless=False)
        page = browser.new_page(viewport={"width": 1440, "height": 900})
        page.goto(url)
        page.wait_for_timeout(wait_ms)          # 렌더링 대기
        page.screenshot(
            path=f"{SAVE_DIR}/{filename}",
            full_page=True
        )
        browser.close()
        print(f"저장 완료: {SAVE_DIR}/{filename}")

# 실행 — 캡처할 페이지 URL과 파일명 지정
capture("https://chatgpt.com",          "chatgpt_session.png")
capture("https://claude.ai",            "claude_session.png")
capture("https://gemini.google.com",    "gemini_session.png")
```

```bash
# 스크립트 실행
python capture_result.py

# 특정 URL만 즉시 캡처 (one-liner)
python -c "
from playwright.sync_api import sync_playwright
with sync_playwright() as p:
    b = p.chromium.launch(); pg = b.new_page()
    pg.goto('https://chatgpt.com'); pg.wait_for_timeout(3000)
    pg.screenshot(path='assignments/$(date +%Y-%m-%d)/screenshots/result.png', full_page=True)
    b.close()
"
```

> **로그인이 필요한 경우** `headless=False`로 실행해 직접 로그인한 뒤, 쿠키를 저장해두면 이후 자동 캡처가 가능합니다.

```python
# 로그인 세션 저장 및 재사용
from playwright.sync_api import sync_playwright

# 최초 1회: 수동 로그인 후 세션 저장
with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    ctx = browser.new_context()
    page = ctx.new_page()
    page.goto("https://claude.ai")
    input("브라우저에서 로그인 완료 후 Enter 키를 누르세요...")
    ctx.storage_state(path="claude_session.json")   # 세션 저장
    browser.close()

# 이후: 저장된 세션으로 자동 캡처
with sync_playwright() as p:
    browser = p.chromium.launch(headless=True)
    ctx = browser.new_context(storage_state="claude_session.json")
    page = ctx.new_page()
    page.goto("https://claude.ai")
    page.wait_for_timeout(3000)
    page.screenshot(path=f"{SAVE_DIR}/claude_result.png", full_page=True)
    browser.close()
```

---

### Step 3-B — 수동 캡처 방법

자동 캡처가 어려운 경우 OS 단축키 또는 도구를 사용합니다.

| OS | 방법 | 단축키 / 도구 |
|----|------|-------------|
| **Windows** | 전체 화면 | `PrtSc` → 그림판 붙여넣기 후 저장 |
| **Windows** | 영역 선택 | `Win + Shift + S` → 클립보드 저장 |
| **Windows** | 스니핑 도구 | 시작 → "캡처 도구" 검색 → 지연 캡처 가능 |
| **macOS** | 전체 화면 | `Cmd + Shift + 3` → 바탕화면에 자동 저장 |
| **macOS** | 영역 선택 | `Cmd + Shift + 4` → 드래그로 영역 지정 |
| **WSL** | 브라우저 캡처 | Windows 단축키 사용 후 `/mnt/c/` 경로로 복사 |

```bash
# WSL에서 Windows 캡처 파일을 프로젝트로 복사
cp /mnt/c/Users/$USER/Pictures/*.png assignments/$(date +%Y-%m-%d)/screenshots/
```

**캡처 시 포함해야 할 화면 요소**
- 사용한 AI 플랫폼 URL (주소창 포함)
- 입력한 프롬프트 전체
- AI 응답 결과 (전체 스크롤 캡처 권장)
- 화면 좌측 하단에 날짜/시간이 보이도록




---

## GitHub MCP 서버 활용 (Claude Desktop / VS Code Copilot)

### MCP(Model Context Protocol)란?

MCP는 AI 모델이 외부 도구·저장소·서비스에 표준화된 방식으로 접근할 수 있게 하는 오픈 프로토콜입니다. **GitHub 공식 MCP 서버**를 설정하면 Claude·Copilot 등의 AI가 이 저장소 파일을 직접 읽고, 이슈를 생성하고, PR을 관리할 수 있습니다.

### 전체 아키텍처

```mermaid
flowchart TD
    subgraph AI클라이언트
        A[Claude Desktop]
        B[VS Code Copilot]
    end
    subgraph MCP레이어
        C[GitHub MCP Server\n@modelcontextprotocol/server-github]
    end
    subgraph GitHub
        D[(자료 저장소\n.md 파일)]
        E[Issues / Discussions]
        F[Pull Requests\n수강생 제출물]
        G[커밋 이력\n버전 관리]
    end
    A -->|MCP 프로토콜| C
    B -->|MCP 프로토콜| C
    C -->|GitHub API| D
    C -->|GitHub API| E
    C -->|GitHub API| F
    C -->|GitHub API| G
```

### Claude Desktop 설정

`~/.config/claude/claude_desktop_config.json`에 추가:

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxxxxxxxxx"
      }
    }
  }
}
```

> GitHub Personal Access Token 발급: **Settings → Developer settings → Personal access tokens → Fine-grained tokens**
> 필요 권한: `Contents (Read/Write)`, `Issues (Read/Write)`, `Pull requests (Read/Write)`

### VS Code + GitHub Copilot MCP 설정

저장소 루트에 `.vscode/mcp.json` 파일 생성:

```json
{
  "servers": {
    "github": {
      "type": "http",
      "url": "https://api.githubcopilot.com/mcp/",
      "headers": {
        "Authorization": "Bearer ${env:GITHUB_TOKEN}"
      }
    }
  }
}
```

---

# 🚀 GitHub Codespaces 완벽 활용 가이드

GitHub Codespaces는 브라우저 또는 VS Code에서 즉시 실행되는 **클라우드 기반 개발 환경**입니다. 로컬 PC에 아무것도 설치하지 않아도 컨테이너 안에서 완전한 개발 환경을 사용할 수 있습니다.

```
┌──────────────────────────────────────────────────────────────────┐
│                   GitHub Codespaces 구조                          │
│                                                                    │
│  GitHub 저장소                                                    │
│       │                                                           │
│       ▼                                                           │
│  Codespace 생성 (.devcontainer/devcontainer.json 읽기)           │
│       │                                                           │
│       ▼                                                           │
│  Azure 클라우드 VM (2~32 vCPU, 4~64 GB RAM)                     │
│       │                                                           │
│       ├── VS Code 서버 (브라우저 / Desktop)                       │
│       ├── 터미널 (zsh / bash)                                    │
│       ├── 포트 포워딩 (8000, 3000, 8080 등)                      │
│       └── GitHub Copilot 자동 연동                               │
└──────────────────────────────────────────────────────────────────┘
```

## Codespaces 무료 사용 한도 (2025년 기준)

| GitHub 플랜 | 월 무료 컴퓨팅 | 월 무료 저장소 |
|------------|--------------|--------------|
| **Free** | 120 코어시간 (2코어 기준 60시간) | 15 GB/월 |
| **Pro** | 180 코어시간 | 20 GB/월 |
| **Team/Enterprise** | 별도 조직 청구 | 별도 조직 청구 |

> 사용량 확인: https://github.com/settings/billing/usage

---

## 1. Codespace 생성 및 시작

### 방법 A — GitHub 웹에서 생성

```
1. 저장소 페이지 접속
2. 초록색 [< > Code] 버튼 클릭
3. [Codespaces] 탭 선택
4. [Create codespace on main] 클릭
   → 또는 [+ New with options...] 로 머신 타입 선택 후 생성
```

### 방법 B — GitHub CLI로 생성

```bash
# GitHub CLI 설치
gh auth login

# 현재 저장소에 Codespace 생성
gh codespace create --repo edumgt/edumgt-lab-init

# 특정 브랜치로 생성
gh codespace create --repo edumgt/edumgt-lab-init --branch develop

# 머신 타입 지정 (2코어/4GB, 4코어/8GB 등)
gh codespace create --repo edumgt/edumgt-lab-init --machine basicLinux32gb

# 생성된 Codespace 목록 확인
gh codespace list

# Codespace에 터미널 접속
gh codespace ssh

# VS Code로 Codespace 열기
gh codespace code
```

### 방법 C — VS Code Desktop에서 연결

```
1. VS Code 확장 [GitHub Codespaces] 설치
2. Ctrl+Shift+P → "Codespaces: Connect to Codespace" 실행
3. GitHub 로그인 후 기존 Codespace 선택 또는 새로 생성
```

---

## 2. devcontainer.json 설정 (개발 환경 자동 구성)

저장소 루트에 `.devcontainer/devcontainer.json` 파일을 추가하면 Codespace 시작 시 개발 환경이 **자동으로 구성**됩니다.

### edumgt-lab-init 전용 devcontainer.json

```json
// .devcontainer/devcontainer.json
{
  "name": "edumgt-lab-init Dev Environment",
  "image": "mcr.microsoft.com/devcontainers/universal:2",

  "features": {
    "ghcr.io/devcontainers/features/python:1": {
      "version": "3.11"
    },
    "ghcr.io/devcontainers/features/node:1": {
      "version": "20"
    },
    "ghcr.io/devcontainers/features/java:1": {
      "version": "17",
      "installMaven": true
    },
    "ghcr.io/devcontainers/features/docker-in-docker:2": {},
    "ghcr.io/devcontainers/features/kubectl-helm-minikube:1": {}
  },

  "customizations": {
    "vscode": {
      "extensions": [
        "GitHub.copilot",
        "GitHub.copilot-chat",
        "ms-python.python",
        "ms-python.vscode-pylance",
        "dbaeumer.vscode-eslint",
        "esbenp.prettier-vscode",
        "vscjava.vscode-java-pack",
        "ms-azuretools.vscode-docker",
        "yzhang.markdown-all-in-one",
        "shd101wyy.markdown-preview-enhanced",
        "mhutchie.git-graph",
        "eamodio.gitlens"
      ],
      "settings": {
        "terminal.integrated.defaultProfile.linux": "bash",
        "python.defaultInterpreterPath": "/usr/local/bin/python",
        "editor.formatOnSave": true,
        "editor.tabSize": 2
      }
    }
  },

  "forwardPorts": [8000, 3000, 8080, 5000],
  "portsAttributes": {
    "8000": { "label": "Python FastAPI", "onAutoForward": "notify" },
    "3000": { "label": "Node.js Express", "onAutoForward": "notify" },
    "8080": { "label": "Spring Boot", "onAutoForward": "notify" }
  },

  "postCreateCommand": "pip install -r lab01-python-app/requirements.txt && npm install --prefix lab02-node-app",

  "remoteEnv": {
    "PYTHONPATH": "${containerWorkspaceFolder}"
  }
}
```

### devcontainer 주요 속성 설명

| 속성 | 설명 | 예시 |
|------|------|------|
| `image` | 기반 컨테이너 이미지 | `mcr.microsoft.com/devcontainers/python:3.11` |
| `features` | 자동 설치할 도구 (Python, Node, Docker 등) | `ghcr.io/devcontainers/features/python:1` |
| `customizations.vscode.extensions` | 자동 설치할 VS Code 확장 | `"GitHub.copilot"` |
| `forwardPorts` | 외부에서 접근 가능하게 할 포트 목록 | `[8000, 3000]` |
| `postCreateCommand` | 컨테이너 생성 후 실행할 스크립트 | `pip install -r requirements.txt` |
| `postStartCommand` | Codespace 시작마다 실행 | `npm run dev` |

---

## 3. Codespaces에서 각 Lab 실행하기

### lab01-python-app (FastAPI)

```bash
# Codespace 터미널에서 실행
cd lab01-python-app
pip install -r requirements.txt
python main.py

# 또는 uvicorn 직접 실행
uvicorn main:app --host 0.0.0.0 --port 8000 --reload

# → 포트 8000이 자동으로 포워딩됨
# → VS Code 하단 PORTS 탭에서 URL 확인 후 브라우저 접속
```

### lab02-node-app (Express)

```bash
cd lab02-node-app
npm install
node index.js

# → 포트 3000 포워딩 후 브라우저에서 접속 가능
```

### lab03-java-app (Spring Boot)

```bash
cd lab03-java-app
mvn clean package -DskipTests
java -jar target/*.jar

# Maven 래퍼 사용 시
./mvnw spring-boot:run

# → 포트 8080 포워딩
```

### Docker-in-Docker 활용 (컨테이너 빌드)

```bash
# Codespace 안에서 Docker 이미지 빌드
docker build -t lab01-python ./lab01-python-app
docker run -p 8000:8000 lab01-python

# Docker Compose 실행
docker compose up -d
```

---

## 4. 포트 포워딩 및 외부 공유

Codespace의 포트를 외부에 공개하면 팀원이 내 개발 서버에 실시간 접속할 수 있습니다.

```
VS Code 하단 → PORTS 탭 → 포트 번호 우클릭
  → [Port Visibility] → [Public] 선택
  → 생성된 URL 공유 (예: https://xxxx-8000.app.github.dev)
```

```bash
# GitHub CLI로 포트 가시성 변경
gh codespace ports visibility 8000:public -c <codespace-name>

# 포트 목록 확인
gh codespace ports -c <codespace-name>
```

> ⚠️ Public 포트는 인증 없이 접근 가능 → 테스트·데모용으로만 사용하고 민감 데이터 노출 주의

---

## 5. Codespace 시크릿 (환경 변수) 관리

API 키, DB 비밀번호 같은 민감 정보를 안전하게 주입합니다.

```
GitHub → Settings → Codespaces → Secrets
  → [New secret] 클릭
  → Name: OPENAI_API_KEY
  → Value: sk-xxxxxxxxxxxx
  → Repository: edumgt/edumgt-lab-init 선택
```

```bash
# Codespace 안에서 사용
echo $OPENAI_API_KEY

# Python 코드에서
import os
api_key = os.environ["OPENAI_API_KEY"]
```

---

## 6. Dotfiles — 나만의 Codespace 환경 세팅

매번 새 Codespace를 만들 때 개인 설정(zsh, vim, git 설정 등)을 자동 적용합니다.

```
GitHub → Settings → Codespaces → Dotfiles
  → Enable dotfiles 체크
  → Dotfiles repository: <본인-아이디>/dotfiles 설정
```

```bash
# dotfiles 저장소 구조 예시
dotfiles/
├── install.sh          # 설치 스크립트 (Codespace 생성 시 자동 실행)
├── .bashrc             # bash 설정
├── .zshrc              # zsh 설정
├── .gitconfig          # git 전역 설정
└── .vimrc              # vim 설정
```

```bash
# install.sh 예시
#!/bin/bash
cp .bashrc ~/.bashrc
cp .gitconfig ~/.gitconfig
echo "Dotfiles applied successfully!"

# git 전역 설정 적용
git config --global user.name "본인 이름"
git config --global user.email "본인 이메일"
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.lg "log --oneline --graph --decorate --all"
```

---

## 7. GitHub Copilot + Codespaces 연동

Codespace에서는 GitHub Copilot이 **자동으로 활성화**됩니다.

```bash
# Copilot Chat으로 코드 설명 요청 (VS Code 내)
# Ctrl+Shift+I → Copilot Chat 패널 열기

# 선택한 코드에 대한 설명 요청
# 코드 블록 선택 → 우클릭 → [Copilot] → [Explain This]

# 코드 수정 제안
# 코드 선택 → Ctrl+I → "/fix 이 코드의 버그를 찾아줘"

# 단위 테스트 생성
# 코드 선택 → Ctrl+I → "/tests 이 함수의 단위 테스트를 작성해줘"
```

### Copilot 주요 슬래시 명령어

| 명령어 | 기능 |
|--------|------|
| `/explain` | 선택한 코드 설명 |
| `/fix` | 버그·오류 수정 제안 |
| `/tests` | 단위 테스트 자동 생성 |
| `/doc` | 함수·클래스 문서 주석 생성 |
| `/optimize` | 코드 성능 최적화 제안 |
| `/simplify` | 코드 단순화·리팩터링 |

---

## 8. Codespace 수명 주기 관리

```bash
# 실행 중인 Codespace 목록
gh codespace list

# Codespace 중지 (요금 절약 — 저장소 유지)
gh codespace stop -c <codespace-name>

# Codespace 재시작
gh codespace code -c <codespace-name>

# Codespace 삭제 (저장소 완전 삭제)
gh codespace delete -c <codespace-name>

# 30일 이상 비활성 Codespace는 자동 삭제됨
# Settings → Codespaces → Default idle timeout 설정 가능
```

> 💡 **비용 절약 팁:** 사용 후 반드시 Stop(중지)하세요. Running 상태에서만 컴퓨팅 요금이 발생합니다. 중지 상태에서는 저장소 비용만 발생합니다.

---

# 🔧 GitHub 핵심 기능 완전 활용 가이드

## GitHub Actions — CI/CD 자동화

GitHub Actions는 코드 푸시, PR 생성, 스케줄 등 이벤트 발생 시 **자동으로 빌드·테스트·배포**를 수행하는 CI/CD 플랫폼입니다.

### 워크플로우 파일 기본 구조

```yaml
# .github/workflows/ci.yml
name: CI Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '0 9 * * 1'   # 매주 월요일 오전 9시 (UTC)

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: 저장소 체크아웃
        uses: actions/checkout@v4

      - name: Python 설정
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: 의존성 설치
        run: |
          pip install -r lab01-python-app/requirements.txt

      - name: 테스트 실행
        run: |
          cd lab01-python-app
          python -m pytest tests/ -v

      - name: 테스트 커버리지 리포트
        run: |
          pip install pytest-cov
          pytest --cov=. --cov-report=xml

      - name: 커버리지 업로드 (Codecov)
        uses: codecov/codecov-action@v4
```

### 실전 워크플로우 예시

```yaml
# .github/workflows/docker-build-push.yml
name: Docker Build & Push

on:
  push:
    branches: [ main ]
    tags: [ 'v*' ]

env:
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  build-push:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write

    steps:
      - uses: actions/checkout@v4

      - name: Docker Buildx 설정
        uses: docker/setup-buildx-action@v3

      - name: GitHub Container Registry 로그인
        uses: docker/login-action@v3
        with:
          registry: ${{ env.REGISTRY }}
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}

      - name: 메타데이터 추출 (태그, 라벨)
        id: meta
        uses: docker/metadata-action@v5
        with:
          images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}
          tags: |
            type=ref,event=branch
            type=semver,pattern={{version}}
            type=sha

      - name: 빌드 및 푸시
        uses: docker/build-push-action@v5
        with:
          context: ./lab01-python-app
          push: true
          tags: ${{ steps.meta.outputs.tags }}
          labels: ${{ steps.meta.outputs.labels }}
          cache-from: type=gha
          cache-to: type=gha,mode=max
```

### Actions 이벤트 트리거 종류

| 트리거 | 예시 | 설명 |
|--------|------|------|
| `push` | `branches: [main]` | 특정 브랜치 푸시 시 |
| `pull_request` | `types: [opened, synchronize]` | PR 생성/갱신 시 |
| `schedule` | `cron: '0 9 * * *'` | 정기 실행 (cron 형식) |
| `workflow_dispatch` | (없음) | 수동 실행 버튼 활성화 |
| `release` | `types: [published]` | 릴리즈 발행 시 |
| `issue_comment` | `types: [created]` | 이슈 댓글 작성 시 |

### 주요 공식 Actions

```yaml
# 코드 체크아웃
- uses: actions/checkout@v4

# 언어 환경 설정
- uses: actions/setup-python@v5
  with: { python-version: '3.11' }
- uses: actions/setup-node@v4
  with: { node-version: '20' }
- uses: actions/setup-java@v4
  with: { java-version: '17', distribution: 'temurin' }

# 캐시 활용 (빌드 속도 향상)
- uses: actions/cache@v4
  with:
    path: ~/.cache/pip
    key: ${{ runner.os }}-pip-${{ hashFiles('**/requirements.txt') }}

# 아티팩트 업로드/다운로드
- uses: actions/upload-artifact@v4
  with: { name: build-output, path: dist/ }
- uses: actions/download-artifact@v4
  with: { name: build-output }

# GitHub Pages 배포
- uses: actions/deploy-pages@v4

# Slack 알림
- uses: slackapi/slack-github-action@v1.26.0
  with:
    payload: '{"text": "✅ 배포 완료: ${{ github.ref_name }}"}'
  env:
    SLACK_WEBHOOK_URL: ${{ secrets.SLACK_WEBHOOK_URL }}
```

### 시크릿 및 환경변수 관리

```bash
# GitHub CLI로 시크릿 설정
gh secret set DOCKER_PASSWORD --body "my-password"
gh secret set AWS_ACCESS_KEY_ID --body "AKIA..."

# 워크플로우에서 시크릿 사용
env:
  DOCKER_PASSWORD: ${{ secrets.DOCKER_PASSWORD }}
  AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}

# 환경별 시크릿 (Environments)
environment: production
env:
  API_KEY: ${{ secrets.PROD_API_KEY }}
```

---

## GitHub Issues — 이슈 관리 고급 활용

### 이슈 템플릿 설정

```yaml
# .github/ISSUE_TEMPLATE/bug_report.yml
name: 🐛 버그 리포트
description: 버그나 오류를 신고해주세요
title: "[BUG] "
labels: ["bug", "needs-triage"]
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        버그를 발견하셨군요! 아래 항목을 최대한 자세히 작성해주세요.

  - type: textarea
    id: bug-description
    attributes:
      label: 버그 설명
      description: 어떤 문제가 발생했나요?
      placeholder: "FastAPI 서버 시작 시 포트 충돌 오류 발생..."
    validations:
      required: true

  - type: textarea
    id: reproduction-steps
    attributes:
      label: 재현 방법
      description: 버그를 재현하는 단계를 작성해주세요
      value: |
        1. `...` 실행
        2. `...` 입력
        3. 오류 메시지 확인
    validations:
      required: true

  - type: dropdown
    id: environment
    attributes:
      label: 실행 환경
      options:
        - Windows 11 + WSL2
        - macOS
        - Linux (Ubuntu)
        - GitHub Codespaces
    validations:
      required: true

  - type: textarea
    id: logs
    attributes:
      label: 오류 로그
      description: 오류 메시지나 로그를 붙여넣어 주세요
      render: shell
```

```yaml
# .github/ISSUE_TEMPLATE/feature_request.yml
name: ✨ 기능 요청
description: 새로운 기능을 제안해주세요
title: "[FEAT] "
labels: ["enhancement"]

body:
  - type: textarea
    id: feature-description
    attributes:
      label: 기능 설명
      description: 어떤 기능이 필요하신가요?
    validations:
      required: true

  - type: textarea
    id: motivation
    attributes:
      label: 필요한 이유
      description: 이 기능이 왜 필요한가요?
    validations:
      required: true
```

### 이슈 레이블 전략

```bash
# GitHub CLI로 레이블 생성
gh label create "bug" --color "d73a4a" --description "버그 및 오류"
gh label create "enhancement" --color "a2eeef" --description "새 기능 요청"
gh label create "documentation" --color "0075ca" --description "문서 개선"
gh label create "good first issue" --color "7057ff" --description "처음 기여자에게 적합"
gh label create "help wanted" --color "008672" --description "도움 필요"
gh label create "priority: high" --color "e11d48" --description "높은 우선순위"
gh label create "priority: low" --color "6ee7b7" --description "낮은 우선순위"
gh label create "in progress" --color "fbbf24" --description "작업 진행 중"

# 이슈 생성 (CLI)
gh issue create \
  --title "[BUG] Python FastAPI 서버 시작 오류" \
  --body "포트 8000이 이미 사용 중일 때 오류 발생" \
  --label "bug,priority: high" \
  --assignee "@me"

# 이슈 목록 확인
gh issue list --label "bug" --state open

# 이슈 닫기
gh issue close 42 --comment "수정 완료 (#43 PR에서 해결)"
```

### 마일스톤 활용

```bash
# 마일스톤 생성
gh api repos/edumgt/edumgt-lab-init/milestones \
  --method POST \
  --field title="v1.0 - 기본 환경 설정 완료" \
  --field due_on="2025-08-31T00:00:00Z" \
  --field description="Python, Node.js, Java, Docker, K8s 환경 구축 완료"

# 이슈에 마일스톤 연결
gh issue edit 42 --milestone "v1.0 - 기본 환경 설정 완료"
```

---

## GitHub Pull Request — 코드 리뷰 고급 활용

### PR 템플릿 설정

```markdown
<!-- .github/pull_request_template.md -->
## 변경 내용 요약
<!-- 어떤 변경을 했는지 간략히 설명하세요 -->

## 변경 유형
- [ ] 🐛 버그 수정 (기존 기능이 정상 동작하도록 수정)
- [ ] ✨ 새 기능 (기존 기능을 손상시키지 않는 새 기능 추가)
- [ ] 💥 Breaking change (기존 기능을 변경하거나 제거)
- [ ] 📝 문서 수정
- [ ] ♻️ 리팩터링 (기능 변경 없이 코드 개선)
- [ ] ✅ 테스트 추가/수정

## 관련 이슈
- Closes #이슈번호

## 테스트 방법
<!-- 변경 사항을 어떻게 테스트했는지 설명하세요 -->
```bash
# 테스트 명령어
python -m pytest tests/ -v
```

## 스크린샷 (UI 변경 시)
<!-- 변경 전후 스크린샷을 첨부해주세요 -->

## 체크리스트
- [ ] 코드 스타일 가이드 준수
- [ ] 단위 테스트 추가/수정
- [ ] 문서(README) 업데이트
- [ ] Breaking change에 대한 공지 포함
```

### 브랜치 보호 규칙 설정

```
GitHub 저장소 → Settings → Branches → [Add rule]

Branch name pattern: main

✅ Require a pull request before merging
   ✅ Require approvals: 1명 이상
   ✅ Dismiss stale pull request approvals when new commits are pushed
   ✅ Require review from Code Owners

✅ Require status checks to pass before merging
   ✅ Require branches to be up to date before merging
   Status checks: CI Pipeline / test

✅ Require conversation resolution before merging
✅ Require signed commits
✅ Include administrators
✅ Restrict who can push to matching branches
```

### CODEOWNERS 파일

```bash
# .github/CODEOWNERS
# 파일/디렉토리별 자동 리뷰어 지정

# 전체 저장소 기본 리뷰어
*                   @edumgt

# Python 관련 변경 시 자동 지정
/lab01-python-app/  @python-lead

# Node.js 관련 변경 시 자동 지정
/lab02-node-app/    @node-lead

# Kubernetes 관련 변경 시 자동 지정
/lab04-k8s/         @devops-lead

# 인프라 설정 변경 시 (복수 지정 가능)
*.yml               @devops-lead @team-lead
*.yaml              @devops-lead @team-lead

# Dockerfile 변경 시
Dockerfile          @devops-lead
```

### PR 리뷰 워크플로우

```bash
# PR 생성 (GitHub CLI)
gh pr create \
  --title "feat: lab01 FastAPI 헬스체크 엔드포인트 추가" \
  --body "$(cat .github/pull_request_template.md)" \
  --base main \
  --head feature/health-check \
  --reviewer "edumgt" \
  --label "enhancement"

# PR 목록 확인
gh pr list --state open

# PR 상세 보기
gh pr view 15

# PR 체크 상태 확인
gh pr checks 15

# PR 승인 (리뷰어 입장)
gh pr review 15 --approve --body "LGTM! 코드 잘 작성됐습니다."

# PR 변경 요청
gh pr review 15 --request-changes --body "테스트 케이스를 추가해주세요."

# PR 머지 (Squash)
gh pr merge 15 --squash --delete-branch

# PR 머지 (일반)
gh pr merge 15 --merge

# PR 머지 (Rebase)
gh pr merge 15 --rebase
```

---

## GitHub Projects — 프로젝트 보드 관리

GitHub Projects는 이슈·PR을 **칸반 보드 또는 스프린트 방식**으로 관리하는 프로젝트 관리 도구입니다.

### 프로젝트 생성 및 설정

```
1. 저장소 → [Projects] 탭 → [New project]
2. 템플릿 선택:
   - Board: 칸반 보드 (To Do / In Progress / Done)
   - Table: 스프레드시트 형식
   - Roadmap: 타임라인/간트 차트
3. 프로젝트 이름 입력 → [Create]
```

### 자동화 규칙 설정

```
Projects → Settings → Workflows

기본 제공 자동화:
  ✅ Item added to project → Status: Todo
  ✅ Item reopened → Status: Todo
  ✅ Item closed → Status: Done
  ✅ Pull request merged → Status: Done

커스텀 자동화 예시:
  When: Pull request is opened
  Filter: label = "in progress"
  Then: Set Status = In Progress
```

### GitHub CLI로 Projects 활용

```bash
# 프로젝트 목록 확인
gh project list --owner edumgt

# 이슈를 프로젝트에 추가
gh project item-add 1 --owner edumgt --url https://github.com/edumgt/edumgt-lab-init/issues/42

# 프로젝트 아이템 상태 변경
gh project item-edit --id <item-id> --field-id <field-id> --project-id 1 --text "In Progress"
```

---

## GitHub Pages — 정적 사이트 무료 호스팅

GitHub Pages를 활용하면 저장소의 HTML/Markdown 파일을 **무료 정적 웹사이트**로 게시할 수 있습니다.

### 설정 방법

```
저장소 → Settings → Pages

Source:
  [Deploy from a branch] 선택
  Branch: main / docs 또는 gh-pages

또는

  [GitHub Actions] 선택 → 워크플로우로 자동 배포
```

### GitHub Actions로 Jekyll 사이트 배포

```yaml
# .github/workflows/pages.yml
name: GitHub Pages 배포

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v4
      - uses: actions/jekyll-build-pages@v1
        with:
          source: ./docs
          destination: ./_site
      - uses: actions/upload-pages-artifact@v3

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - uses: actions/deploy-pages@v4
        id: deployment
```

### 커스텀 도메인 설정

```bash
# CNAME 파일 생성 (docs/ 또는 루트)
echo "lab.edumgt.com" > CNAME

# DNS 설정 (도메인 공급자에서)
# Type: CNAME
# Name: lab
# Value: edumgt.github.io
```

---

## GitHub Discussions — 커뮤니티 토론

GitHub Discussions는 Q&A, 아이디어 공유, 공지사항 등 **커뮤니티 소통**을 위한 포럼입니다.

```
저장소 → Settings → Features → ✅ Discussions 활성화
```

### 카테고리 활용

| 카테고리 | 용도 | 예시 |
|----------|------|------|
| 📣 Announcements | 공지사항 | 새 Lab 추가 안내 |
| 💡 Ideas | 아이디어 제안 | 새 실습 주제 제안 |
| ❓ Q&A | 질문과 답변 | 환경 설정 문의 |
| 🙏 Show and tell | 결과물 공유 | 완성한 프로젝트 공유 |
| 🗳️ Polls | 투표 | 다음 회차 주제 투표 |

```bash
# GitHub CLI로 Discussion 생성
gh api graphql -f query='
mutation {
  createDiscussion(input: {
    repositoryId: "저장소ID"
    categoryId: "카테고리ID"
    title: "lab01 실행 시 자주 발생하는 오류 Q&A"
    body: "FastAPI 실행 관련 질문은 여기에 남겨주세요."
  }) {
    discussion { url }
  }
}'
```

---

## GitHub Packages — 패키지 레지스트리

GitHub Packages는 Docker 이미지, npm, Maven, PyPI 등 패키지를 **GitHub 저장소와 통합하여 관리**하는 레지스트리입니다.

### Docker 이미지 배포 (GitHub Container Registry)

```bash
# 1. GitHub Container Registry(GHCR) 로그인
echo $GITHUB_TOKEN | docker login ghcr.io -u <github-username> --password-stdin

# 2. 이미지 빌드 및 태깅
docker build -t ghcr.io/edumgt/edumgt-lab-init/lab01-python:latest ./lab01-python-app
docker build -t ghcr.io/edumgt/edumgt-lab-init/lab02-node:latest ./lab02-node-app

# 3. 이미지 푸시
docker push ghcr.io/edumgt/edumgt-lab-init/lab01-python:latest
docker push ghcr.io/edumgt/edumgt-lab-init/lab02-node:latest

# 4. 이미지 풀 (다른 환경에서)
docker pull ghcr.io/edumgt/edumgt-lab-init/lab01-python:latest
docker run -p 8000:8000 ghcr.io/edumgt/edumgt-lab-init/lab01-python:latest
```

### Actions에서 GHCR 자동 배포

```yaml
- name: GHCR 로그인
  uses: docker/login-action@v3
  with:
    registry: ghcr.io
    username: ${{ github.actor }}
    password: ${{ secrets.GITHUB_TOKEN }}   # 별도 시크릿 불필요

- name: 빌드 및 GHCR 푸시
  uses: docker/build-push-action@v5
  with:
    context: ./lab01-python-app
    push: true
    tags: ghcr.io/${{ github.repository }}/lab01-python:${{ github.sha }}
```

---

## GitHub Security — 보안 자동화

### Dependabot — 의존성 자동 업데이트

```yaml
# .github/dependabot.yml
version: 2
updates:
  # Python 의존성
  - package-ecosystem: "pip"
    directory: "/lab01-python-app"
    schedule:
      interval: "weekly"
      day: "monday"
      time: "09:00"
      timezone: "Asia/Seoul"
    reviewers:
      - "edumgt"
    labels:
      - "dependencies"
    open-pull-requests-limit: 5

  # Node.js 의존성
  - package-ecosystem: "npm"
    directory: "/lab02-node-app"
    schedule:
      interval: "weekly"
    ignore:
      - dependency-name: "express"
        update-types: ["version-update:semver-major"]

  # Java (Maven) 의존성
  - package-ecosystem: "maven"
    directory: "/lab03-java-app"
    schedule:
      interval: "monthly"

  # Docker 베이스 이미지
  - package-ecosystem: "docker"
    directory: "/lab01-python-app"
    schedule:
      interval: "weekly"

  # GitHub Actions
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "weekly"
```

### Code Scanning (CodeQL)

```yaml
# .github/workflows/codeql.yml
name: CodeQL 보안 스캔

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
  schedule:
    - cron: '0 2 * * 1'  # 매주 월요일 새벽 2시

jobs:
  analyze:
    runs-on: ubuntu-latest
    permissions:
      security-events: write
      actions: read
      contents: read

    strategy:
      matrix:
        language: ['python', 'javascript', 'java']

    steps:
      - uses: actions/checkout@v4

      - name: CodeQL 초기화
        uses: github/codeql-action/init@v3
        with:
          languages: ${{ matrix.language }}

      - name: 자동 빌드
        uses: github/codeql-action/autobuild@v3

      - name: CodeQL 분석 실행
        uses: github/codeql-action/analyze@v3
        with:
          category: "/language:${{matrix.language}}"
```

### 시크릿 스캐닝 (Secret Scanning)

```
저장소 → Settings → Security → Secret scanning

✅ Secret scanning 활성화
✅ Push protection 활성화
   → API 키, 비밀번호가 코드에 포함된 상태로 push 시 자동 차단

알림 수신: 시크릿이 감지되면 이메일 + Security 탭에 알림
```

```bash
# .gitignore로 시크릿 파일 제외
echo ".env" >> .gitignore
echo "*.pem" >> .gitignore
echo "credentials.json" >> .gitignore
echo "secrets.yaml" >> .gitignore

# .env 예시 (절대 커밋하지 마세요)
# OPENAI_API_KEY=sk-xxxxxxxxxxxx
# DATABASE_URL=postgresql://****@localhost:5432/db
# AWS_SECRET_ACCESS_KEY=xxxxxxxxxxxxxxxxxxxx
```

---

## GitHub CLI (gh) 완전 명령어 가이드

### 설치 및 인증

```bash
# 설치 (Windows — winget)
winget install --id GitHub.cli

# 설치 (macOS — Homebrew)
brew install gh

# 설치 (Linux/WSL — Ubuntu)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update && sudo apt install gh

# GitHub 인증
gh auth login
# → GitHub.com 선택 → HTTPS → 브라우저 인증

# 인증 상태 확인
gh auth status

# 토큰 방식 인증 (CI 환경)
echo $GITHUB_TOKEN | gh auth login --with-token
```

### 저장소 관련 명령어

```bash
# 저장소 생성
gh repo create edumgt-lab-init --public --description "개발환경 초기 설정 가이드"

# 저장소 클론
gh repo clone edumgt/edumgt-lab-init

# 저장소 정보 조회
gh repo view edumgt/edumgt-lab-init

# 저장소 Fork
gh repo fork edumgt/edumgt-lab-init --clone

# 저장소 토픽 설정
gh repo edit edumgt/edumgt-lab-init --add-topic "devops,kubernetes,docker,ai"

# 저장소 가시성 변경
gh repo edit edumgt/edumgt-lab-init --visibility public
```

### 이슈 명령어

```bash
# 이슈 생성
gh issue create --title "제목" --body "내용" --label "bug" --assignee "@me"

# 이슈 목록 (JSON 출력)
gh issue list --json number,title,labels,assignees --limit 20

# 이슈 필터링
gh issue list --label "bug" --state open --assignee "@me"

# 이슈 코멘트 추가
gh issue comment 42 --body "확인했습니다. 내일까지 수정하겠습니다."

# 이슈 닫기
gh issue close 42

# 이슈 재오픈
gh issue reopen 42
```

### PR 명령어

```bash
# PR 생성
gh pr create --fill  # 커밋 메시지로 자동 채우기

# PR 상태 확인
gh pr status

# PR 체크아웃 (다른 사람 PR 로컬에서 검토)
gh pr checkout 15

# PR 차이 확인
gh pr diff 15

# PR 머지 후 브랜치 삭제
gh pr merge 15 --squash --delete-branch --auto

# Draft PR 생성
gh pr create --draft --title "WIP: 작업 중"

# PR Ready 상태로 변경
gh pr ready 15
```

### Actions 명령어

```bash
# 워크플로우 목록 확인
gh workflow list

# 워크플로우 수동 실행
gh workflow run ci.yml --ref main

# 워크플로우 실행 이력
gh run list --workflow ci.yml --limit 10

# 실행 중인 워크플로우 로그 확인
gh run watch

# 특정 실행의 로그 확인
gh run view 1234567890 --log

# 실패한 워크플로우 재실행
gh run rerun 1234567890

# 워크플로우 활성화/비활성화
gh workflow enable ci.yml
gh workflow disable ci.yml
```

### 시크릿 명령어

```bash
# 저장소 시크릿 설정
gh secret set OPENAI_API_KEY
gh secret set DATABASE_URL --body "postgresql://..."

# 시크릿 목록 확인 (이름만 표시)
gh secret list

# 시크릿 삭제
gh secret delete OPENAI_API_KEY

# 환경별 시크릿
gh secret set PROD_API_KEY --env production
gh secret set DEV_API_KEY --env development
```

### API 직접 호출 (고급)

```bash
# REST API 직접 호출
gh api repos/edumgt/edumgt-lab-init

# 저장소 통계
gh api repos/edumgt/edumgt-lab-init/stats/contributors

# 이슈 일괄 생성 (JSON 파일 사용)
gh api repos/edumgt/edumgt-lab-init/issues \
  --method POST \
  --input issue-data.json

# GraphQL 쿼리
gh api graphql -f query='
query {
  repository(owner: "edumgt", name: "edumgt-lab-init") {
    issues(states: OPEN, first: 10) {
      nodes {
        number
        title
        createdAt
      }
    }
  }
}'
```

---

## GitHub 고급 기능 요약

### GitHub Wiki

```
저장소 → Settings → Features → ✅ Wikis 활성화
저장소 → Wiki 탭 → [New page]

# Wiki를 로컬에서 편집
git clone https://github.com/edumgt/edumgt-lab-init.wiki.git
cd edumgt-lab-init.wiki
# .md 파일 편집 후 push
```

### GitHub Releases

```bash
# 릴리즈 생성 (태그 + 릴리즈 노트)
gh release create v1.0.0 \
  --title "v1.0.0 - 기본 환경 설정 완료" \
  --notes "## 변경 사항
  - Python FastAPI 환경 구성
  - Node.js Express 환경 구성
  - Docker 컨테이너 빌드 추가" \
  --latest

# 아티팩트 첨부
gh release create v1.0.0 dist/*.tar.gz dist/*.zip \
  --title "v1.0.0" \
  --generate-notes  # 커밋 기반 자동 릴리즈 노트 생성

# 릴리즈 목록
gh release list

# 최신 릴리즈 정보
gh release view --json tagName,publishedAt,assets
```

### GitHub Gist — 코드 스니펫 공유

```bash
# Gist 생성 (공개)
gh gist create main.py --public --desc "FastAPI 헬스체크 예제"

# Gist 생성 (비공개)
gh gist create .env.example --desc "환경변수 예시 파일"

# 여러 파일로 Gist 생성
gh gist create main.py requirements.txt Dockerfile --public

# Gist 목록
gh gist list

# Gist 편집
gh gist edit <gist-id>
```

### GitHub Insights — 저장소 분석

```
저장소 → Insights 탭

주요 통계:
  - Contributors: 기여자별 커밋 수, 추가/삭제 라인
  - Traffic: 저장소 방문자, 클론 수
  - Commits: 시간별 커밋 활동량
  - Code frequency: 코드 추가/삭제 추이
  - Dependency graph: 의존성 시각화
  - Forks: Fork 현황
```

---

## AI 기반 개발자 페르소나 예시 10선

PTCF 프레임워크의 **Persona** 요소로 프롬프트 앞에 삽입하여 사용합니다.
개발 실무 맥락에 맞는 역할을 AI에게 부여하면 출력의 기술적 정확성과 실용성이 크게 높아집니다.

| # | 페르소나 | 프롬프트 설정 문구 |
|---|---------|-----------------|
| 1 | **시니어 백엔드 아키텍트** | "당신은 10년 경력의 시니어 백엔드 아키텍트입니다. FastAPI·Spring Boot·Node.js 중 주어진 요구사항에 가장 적합한 기술 스택을 선정하고, 확장성·유지보수성·팀 러닝 커브 기준으로 근거를 제시하십시오." |
| 2 | **DevOps/MLOps 엔지니어** | "당신은 Docker·Kubernetes·GitLab CI 전문 DevOps 엔지니어입니다. 제시된 애플리케이션을 컨테이너화하고, 무중단 배포(Rolling Update 또는 Blue-Green) 전략을 Kubernetes YAML과 함께 설계하십시오." |
| 3 | **LLM 애플리케이션 개발자** | "당신은 LangChain·RAG·프롬프트 엔지니어링 전문가입니다. 제시된 도메인 요구사항에 맞는 RAG 파이프라인 아키텍처를 설계하고, 청킹 전략·임베딩 모델·벡터 DB 선택 근거를 포함하십시오." |
| 4 | **코드 리뷰어** | "당신은 클린 코드와 SOLID 원칙에 정통한 시니어 개발자입니다. 제시된 코드를 리뷰하여 (1) 버그 및 잠재적 오류, (2) 성능 병목, (3) 가독성·유지보수성 개선점을 항목별로 지적하고 수정 코드를 제안하십시오." |
| 5 | **보안 전문가 (AppSec)** | "당신은 OWASP Top 10에 정통한 애플리케이션 보안 전문가입니다. 제시된 코드 또는 아키텍처에서 SQL 인젝션·XSS·인증 취약점·민감 정보 노출 위험을 식별하고, 각 취약점별 수정 방법과 방어 코드를 제시하십시오." |
| 6 | **데이터 엔지니어** | "당신은 Python·Airflow·Kafka·Spark 경험이 풍부한 데이터 엔지니어입니다. 제시된 데이터 수집·변환·적재 요구사항을 분석하여 ELT/ETL 파이프라인 설계안과 스케줄링 전략을 코드 예시와 함께 제시하십시오." |
| 7 | **클라우드 비용 최적화 전문가** | "당신은 AWS 비용 최적화 전문 솔루션 아키텍트입니다. 제시된 AWS 아키텍처를 분석하여 Reserved Instance·Spot Instance·Auto Scaling 전략으로 월 비용을 30% 이상 절감하는 방안을 구체적 수치와 함께 제시하십시오." |
| 8 | **API 설계 전문가** | "당신은 RESTful API 및 OpenAPI 스펙 설계 전문가입니다. 제시된 요구사항을 바탕으로 REST API 엔드포인트를 설계하고, HTTP 메서드·상태 코드·응답 스키마·에러 처리를 OpenAPI 3.0 YAML 형식으로 작성하십시오." |
| 9 | **ML 모델 최적화 전문가** | "당신은 PyTorch·HuggingFace 기반 모델 경량화 전문가입니다. 제시된 모델의 추론 속도와 메모리 사용량을 줄이기 위한 Quantization·Pruning·Knowledge Distillation 전략을 비교하고 각 기법의 정확도-속도 트레이드오프를 분석하십시오." |
| 10 | **기술 문서 작성 전문가** | "당신은 개발자 경험(DX) 중심의 기술 문서 전문가입니다. 제시된 API 또는 라이브러리에 대한 README·사용 가이드·코드 예제를 작성하십시오. 초보자도 5분 안에 시작할 수 있도록 Quick Start를 먼저 작성하고, 상세 레퍼런스는 이후에 배치하십시오." |

### 복합 페르소나 활용 예시

단일 페르소나보다 **역할을 조합**하면 더 입체적인 분석이 가능합니다.

```
# 예시 1: 아키텍처 리뷰 복합 페르소나
"당신은 시니어 백엔드 아키텍트이면서 AWS 비용 최적화 전문가입니다.
 아래 시스템 아키텍처를 (1) 확장성, (2) 비용, (3) 운영 복잡도 세 축으로 평가하고
 각 항목별 1~5점 점수와 개선 제안을 표 형식으로 제시하십시오.
 [아키텍처 다이어그램 또는 설명]"

# 예시 2: 코드 보안 리뷰 복합 페르소나
"당신은 클린 코드 전문 코드 리뷰어이자 AppSec 전문가입니다.
 아래 FastAPI 코드를 리뷰하여 (1) 코드 품질 문제와 (2) 보안 취약점을 각각 구분하여
 우선순위와 수정 코드를 함께 제시하십시오.
 [코드 붙여넣기]"
```


---

# 개발환경 기본 설정

## 시작 전 개인 준비 요약 (필독)

이 저장소는 **Python(FastAPI) · Node.js(Express) · Java(Spring Boot) · Docker · Kubernetes · VMware 가상머신**을 순차적으로 실습하는 구조입니다.  
아래 항목을 먼저 개인 기준으로 채워두면 이후 실습 진행 속도가 크게 빨라집니다.

### 1) 개인별 습득 기술 스택 (필수/권장)

| 구분 | 필수 수준 | 저장소 기준 학습 포인트 |
|------|-----------|--------------------------|
| Python 3.11+ | 기초 문법 + 패키지 설치 가능 | `lab01-python-app`에서 FastAPI/uvicorn 실행, `requirements.txt` 이해 |
| Node.js 20+ | npm, 모듈 실행 가능 | `lab02-node-app`에서 Express 서버 실행 및 헬스체크 확인 |
| Java 17 + Maven | 빌드/테스트 실행 가능 | `lab03-java-app`에서 `mvn test`, Spring Boot 기동 |
| Docker | 이미지 빌드/컨테이너 실행 가능 | 각 lab의 `Dockerfile` 빌드 및 실행 |
| Kubernetes 기초 | Deployment/Service YAML 이해 | `lab04-k8s/*.yaml` 배포 구조 이해 |
| VMware 가상머신 구성 | VM 생성/네트워크/스냅샷 관리 | `lab05-vmware-vm`에서 kubeadm 클러스터용 노드 준비 |
| Git/GitHub | clone/branch/commit/PR | 팀 협업 및 과제 제출 기본 흐름 수행 |
| VS Code | 확장 설치, 터미널 사용 | 언어별 실습 코드 실행/디버깅 |

### 2) 본인 PC 사양 점검 기준 (개인 기록용)

| 항목 | 최소 권장 | 팀 프로젝트 권장 | 내 PC 실측값(작성) |
|------|-----------|------------------|--------------------|
| CPU | 4코어 8스레드 이상 | 8코어 16스레드 이상 | |
| RAM | 16GB | 32GB 이상 | |
| 저장공간 | 여유 50GB 이상(SSD 권장) | 여유 100GB 이상(NVMe 권장) | |
| 운영체제 | Windows 10/11 + WSL2 | Windows 11 + WSL2 최신 | |
| 네트워크 | 유선 또는 안정적인 Wi-Fi | 유선 LAN 우선 | |

- 아래 PC/네트워크 점검 섹션의 명령어로 실측값을 먼저 채우세요.
- Docker/VM/K8s 실습 시 메모리 부족이 가장 큰 병목이므로, 여유 RAM 확인을 최우선으로 권장합니다.

### 3) 가입해야 할 플랫폼 (개인 체크리스트)

실습 진행 전 아래 계정을 동일 이메일 기준으로 준비하세요.

- [ ] Gmail (기준 이메일/복구 수단)
- [ ] GitHub (2FA 활성화)
- [ ] Slack (팀 커뮤니케이션)
- [ ] Docker Hub (이미지 푸시/풀)
- [ ] AWS (MFA + 예산 알림 설정)

> 상세 가입 절차는 아래 **필수 플랫폼 계정 준비** 섹션을 그대로 따르면 됩니다.

### 4) 예상 비용(카드 청구 예상금액)

아래 금액은 개인 실습 기준의 **보수적 예상 범위**입니다. (환율/사용량에 따라 변동)

| 항목 | 필수 여부 | 월 예상 비용(USD) | 월 예상 비용(KRW, 환율에 따라 변동) | 비고 |
|------|-----------|-------------------|-----------------------------------------|------|
| Gmail | 필수 | 0 | 0원 | 개인 무료 |
| GitHub | 필수(Free 사용) | 0 | 0원 | 유료 플랜은 선택 |
| Slack | 필수(Free 사용) | 0 | 0원 | 팀 정책에 따라 유료 가능 |
| Docker Hub | 필수(Free 사용) | 0 | 0원 | 사용량 초과 시 유료 전환 가능 |
| AWS 실습 | 필수(가입) | 0 ~ 20 | 0 ~ 약 27,000원 | 프리티어 내 사용 권장, 초과 시 과금 |
| 선택: GitHub Copilot Individual | 선택 | 10 | 약 13,500원 | 학생/오픈소스 기여자는 무료 가능 |
| 선택: OpenAI/Claude/Gemini API | 선택 | 5 ~ 30+ | 약 6,750 ~ 40,500원+ | 호출량 기반 종량제 |
| 선택: Ollama + 로컬 모델 | 선택 | 0 | 0원 | 로컬 PC 자원(RAM/디스크) 추가 사용 |

- **최소 시나리오(필수만, 프리티어 준수)**: 월 **0 ~ 약 27,000원**
- **권장 시나리오(필수 + Copilot)**: 월 **약 13,500 ~ 40,500원**
- AWS는 가입 직후 결제 수단 검증용 소액 승인(임시 결제/환불)이 발생할 수 있으므로 카드 알림을 켜두세요.

---

## AI 기반 비용 체크는 매일 오전 오후 체크해야 합니다.

- https://github.com/settings/billing/usage
- https://platform.openai.com/usage
- https://claude.ai/settings/usage

## 0) PC 기본 정보 및 네트워크 환경 확인 (PowerShell)

> 팀 프로젝트를 시작하기 전, 본인 PC의 하드웨어 사양과 네트워크 환경을 파악해두면 개발 환경 구성 및 팀원 간 자원 공유가 훨씬 수월해집니다.  
> 아래 명령어는 모두 **Windows PowerShell** (또는 **PowerShell 7 이상**) 에서 실행합니다.

---

### 0-1) CPU 정보 확인

```powershell
# CPU 이름, 코어 수, 논리 프로세서(스레드) 수
Get-CimInstance -ClassName Win32_Processor |
    Select-Object Name, NumberOfCores, NumberOfLogicalProcessors, MaxClockSpeed

# 간단 요약 (한 줄)
(Get-CimInstance Win32_Processor).Name
```

---

예상 출력 예시:
```
Name                                       NumberOfCores NumberOfLogicalProcessors MaxClockSpeed
----                                       ------------- ------------------------- -------------
Intel(R) Core(TM) i7-12700H CPU @ 2.30GHz            14                        20          2304
```

---

### 0-2) 메모리(RAM) 정보 확인

```powershell
# 전체 물리 메모리 (GB 단위)
$mem = Get-CimInstance Win32_ComputerSystem
[math]::Round($mem.TotalPhysicalMemory / 1GB, 2)

# 현재 사용 중인 메모리와 여유 메모리
$os = Get-CimInstance Win32_OperatingSystem
[PSCustomObject]@{
    "전체(GB)"  = [math]::Round($os.TotalVisibleMemorySize / 1MB, 2)
    "사용중(GB)" = [math]::Round(($os.TotalVisibleMemorySize - $os.FreePhysicalMemory) / 1MB, 2)
    "여유(GB)"  = [math]::Round($os.FreePhysicalMemory / 1MB, 2)
}

# 메모리 슬롯별 세부 정보 (용량, 속도, 제조사)
Get-CimInstance Win32_PhysicalMemory |
    Select-Object BankLabel, Capacity, Speed, Manufacturer |
    Format-Table -AutoSize
```

---

### 0-3) 디스크 용량 확인

```powershell
# 드라이브별 전체/사용/여유 용량 (GB)
Get-PSDrive -PSProvider FileSystem |
    Select-Object Name,
        @{N="전체(GB)"; E={[math]::Round($_.Used/1GB + $_.Free/1GB, 2)}},
        @{N="사용(GB)"; E={[math]::Round($_.Used/1GB, 2)}},
        @{N="여유(GB)"; E={[math]::Round($_.Free/1GB, 2)}} |
    Format-Table -AutoSize

# 물리 디스크 모델·타입 확인 (HDD/SSD 구분)
Get-PhysicalDisk |
    Select-Object FriendlyName, MediaType, Size, HealthStatus |
    Format-Table -AutoSize

# 디스크 파티션 상세 정보
Get-CimInstance Win32_LogicalDisk |
    Where-Object { $_.DriveType -eq 3 } |
    Select-Object DeviceID,
        @{N="전체(GB)"; E={[math]::Round($_.Size/1GB, 2)}},
        @{N="여유(GB)"; E={[math]::Round($_.FreeSpace/1GB, 2)}},
        @{N="사용률(%)"; E={[math]::Round((1 - $_.FreeSpace/$_.Size)*100, 1)}} |
    Format-Table -AutoSize
```

---

### 0-4) 시스템 전체 요약 한 번에 보기

```powershell
# OS, CPU, 메모리, 호스트명 한 번에 확인
Get-ComputerInfo |
    Select-Object CsName, OsName, OsVersion, OsArchitecture,
                  CsProcessors, CsNumberOfLogicalProcessors,
                  @{N="RAM(GB)"; E={[math]::Round($_.CsTotalPhysicalMemory/1GB,2)}}

# Windows 시스템 정보 (전통적인 방법)
systeminfo | Select-String "Host Name|OS|Processor|Total Physical"
```

---

### 0-5) 네트워크 어댑터 목록 확인

```powershell
# 활성화된 네트워크 어댑터 전체 목록
Get-NetAdapter | Select-Object Name, InterfaceDescription, Status, MacAddress, LinkSpeed

# 연결된(Up 상태) 어댑터만 필터링
Get-NetAdapter | Where-Object { $_.Status -eq "Up" }
```

---

### 0-6) 유선(Ethernet) 네트워크 설정 확인

```powershell
# 유선 어댑터의 IP, 서브넷, 게이트웨이, DNS 확인
Get-NetAdapter | Where-Object { $_.InterfaceDescription -match "Ethernet|Realtek|Intel.*Ethernet" -and $_.Status -eq "Up" } |
    ForEach-Object {
        $adapter = $_
        $ip = Get-NetIPAddress -InterfaceIndex $adapter.InterfaceIndex -AddressFamily IPv4 -ErrorAction SilentlyContinue
        $gw = Get-NetRoute -InterfaceIndex $adapter.InterfaceIndex -DestinationPrefix "0.0.0.0/0" -ErrorAction SilentlyContinue
        $dns = Get-DnsClientServerAddress -InterfaceIndex $adapter.InterfaceIndex -AddressFamily IPv4 -ErrorAction SilentlyContinue
        [PSCustomObject]@{
            어댑터      = $adapter.Name
            IP주소      = $ip.IPAddress
            서브넷길이  = $ip.PrefixLength
            게이트웨이  = $gw.NextHop
            DNS서버     = ($dns.ServerAddresses -join ", ")
            MAC주소     = $adapter.MacAddress
            링크속도    = $adapter.LinkSpeed
        }
    } | Format-List

# DHCP 또는 고정 IP 여부 확인
Get-NetIPConfiguration | Where-Object { $_.InterfaceAlias -match "Ethernet" } |
    Select-Object InterfaceAlias, IPv4Address, IPv4DefaultGateway, DNSServer
```

---

### 0-7) 무선(Wi-Fi) 네트워크 설정 확인

```powershell
# Wi-Fi 어댑터 정보 및 현재 연결 상태
Get-NetAdapter | Where-Object { $_.InterfaceDescription -match "Wi-Fi|Wireless|802.11" }

# 현재 연결된 Wi-Fi SSID 및 신호 세기
netsh wlan show interfaces

# 저장된 Wi-Fi 프로필 목록 조회
netsh wlan show profiles

# 특정 Wi-Fi 프로필의 비밀번호 확인 (관리자 권한 필요)
# netsh wlan show profile name="<SSID이름>" key=clear

# Wi-Fi 어댑터의 IP 설정 확인
Get-NetIPConfiguration | Where-Object { $_.InterfaceAlias -match "Wi-Fi|WiFi|Wireless" } |
    Select-Object InterfaceAlias, IPv4Address, IPv4DefaultGateway, DNSServer

# 주변 Wi-Fi 네트워크 스캔
netsh wlan show networks mode=bssid
```

---

### 0-8) IP 주소 및 연결 상태 종합 확인

```powershell
# 모든 어댑터의 IP 주소 (IPv4/IPv6) 확인
Get-NetIPAddress | Where-Object { $_.AddressFamily -eq "IPv4" -and $_.IPAddress -ne "127.0.0.1" } |
    Select-Object InterfaceAlias, IPAddress, PrefixLength, PrefixOrigin |
    Format-Table -AutoSize

# 라우팅 테이블 확인
Get-NetRoute -AddressFamily IPv4 | Where-Object { $_.NextHop -ne "0.0.0.0" } |
    Select-Object DestinationPrefix, NextHop, InterfaceAlias, RouteMetric |
    Format-Table -AutoSize

# 인터넷 연결 테스트 (Google DNS ping)
Test-Connection -ComputerName 8.8.8.8 -Count 4

# 특정 도메인 DNS 조회
Resolve-DnsName google.com

# 열려 있는 포트와 연결 상태 확인
Get-NetTCPConnection | Where-Object { $_.State -eq "Established" } |
    Select-Object LocalAddress, LocalPort, RemoteAddress, RemotePort, State |
    Format-Table -AutoSize
```

---

### 0-9) 팀 단위 네트워크 공유 설정

팀원들이 같은 LAN(로컬 네트워크) 환경에서 파일·폴더를 공유하거나 서버에 접근할 수 있도록 설정하는 방법입니다.

#### ① 폴더 공유 (SMB/Windows 파일 공유)

```powershell
# 공유할 폴더 생성 (예: C:\TeamShare)
New-Item -ItemType Directory -Path "C:\TeamShare" -Force

# SMB 공유 생성 (팀원 전체에게 읽기/쓰기 권한)
New-SmbShare -Name "TeamShare" -Path "C:\TeamShare" -FullAccess "Everyone"

# 현재 공유 폴더 목록 확인
Get-SmbShare

# 공유에 접속 중인 세션 확인
Get-SmbSession

# 공유 폴더에 접근하는 방법 (다른 팀원 PC에서 실행)
# \\<공유하는PC의IP>\TeamShare  ← 파일 탐색기 주소창에 입력
# 또는 PowerShell에서:
# net use Z: \\192.168.1.100\TeamShare
```

#### ② 공유 폴더 접근 (팀원 PC에서 네트워크 드라이브 연결)

```powershell
# 네트워크 드라이브 연결 (Z: 드라이브로 매핑)
New-PSDrive -Name "Z" -PSProvider FileSystem -Root "\\192.168.1.100\TeamShare" -Persist

# 또는 net use 명령어로 연결
net use Z: \\192.168.1.100\TeamShare /persistent:yes

# 연결된 네트워크 드라이브 확인
Get-PSDrive -PSProvider FileSystem | Where-Object { $_.DisplayRoot -like "\\*" }
net use

# 네트워크 드라이브 연결 해제
Remove-PSDrive -Name "Z"
net use Z: /delete
```

#### ③ 팀원 PC 검색 및 연결 가능 여부 확인

```powershell
# 같은 네트워크의 PC 목록 스캔 (네트워크 대역 192.168.1.0/24 예시)
1..254 | ForEach-Object {
    $ip = "192.168.1.$_"
    if (Test-Connection -ComputerName $ip -Count 1 -Quiet -TimeoutSeconds 1) {
        [PSCustomObject]@{ IP = $ip; Status = "응답함" }
    }
} | Format-Table -AutoSize

---

# PowerShell IP 스캔 스크립트 정리

## 문제 원인

`-TimeoutSeconds` 파라미터는 PowerShell 6+에서만 지원됩니다.\
Windows PowerShell 5.x에서는 사용할 수 없습니다.

------------------------------------------------------------------------

## 해결 방법 1 (기본)

``` powershell
1..254 | ForEach-Object {
    $ip = "192.168.1.$_"
    if (Test-Connection -ComputerName $ip -Count 1 -Quiet) {
        [PSCustomObject]@{ IP = $ip; Status = "응답함" }
    }
} | Format-Table -AutoSize
```

단점: 기본 타임아웃이라 속도가 느릴 수 있음

------------------------------------------------------------------------

## 해결 방법 2 (추천)

``` powershell
1..254 | ForEach-Object {
    $ip = "192.168.1.$_"
    if (Test-Connection -ComputerName $ip -Count 1 -Quiet -TimeoutMilliseconds 500) {
        [PSCustomObject]@{ IP = $ip; Status = "응답함" }
    }
} | Format-Table -AutoSize
```

장점: 속도 개선

------------------------------------------------------------------------

## 해결 방법 3 (.NET Ping 사용 - 빠름)

``` powershell
1..254 | ForEach-Object {
    $ip = "192.168.1.$_"
    $ping = New-Object System.Net.NetworkInformation.Ping
    try {
        if ($ping.Send($ip, 300).Status -eq "Success") {
            [PSCustomObject]@{ IP = $ip; Status = "응답함" }
        }
    } catch {}
} | Format-Table -AutoSize
```

장점: 가장 빠른 방식

------------------------------------------------------------------------

## PowerShell 7 이상 (병렬 처리)

``` powershell
1..254 | ForEach-Object -Parallel {
    $ip = "192.168.1.$_"
    if (Test-Connection -ComputerName $ip -Count 1 -Quiet -TimeoutSeconds 1) {
        [PSCustomObject]@{ IP = $ip; Status = "응답함" }
    }
} -ThrottleLimit 50
```

장점: 초고속 병렬 스캔

------------------------------------------------------------------------

## 정리

  방법                   속도        권장
  ---------------------- ----------- ---------
  기본 Test-Connection   느림        ❌
  TimeoutMilliseconds    보통        ✅
  .NET Ping              빠름        ⭐ 추천
  병렬 (PS7)             매우 빠름   🚀 최고


---

# 특정 팀원 PC IP로 Ping 테스트
Test-Connection -ComputerName 192.168.1.100 -Count 4

# 특정 포트 열려 있는지 확인 (예: 8080 포트)
Test-NetConnection -ComputerName 192.168.1.100 -Port 8080

# 호스트명으로 IP 조회
[System.Net.Dns]::GetHostAddresses("팀원PC이름")

# ARP 테이블에서 같은 네트워크 장비 목록 확인
arp -a
```

#### ④ Windows 방화벽 설정 (공유 허용)

```powershell
# 파일 및 프린터 공유 방화벽 규칙 활성화 (공유 서버 역할 PC에서 실행)
Enable-NetFirewallRule -DisplayGroup "파일 및 프린터 공유"

# 또는 특정 포트 허용 (예: 개발 서버 포트 8080 개방)
New-NetFirewallRule -DisplayName "DevServer 8080" `
    -Direction Inbound -Protocol TCP -LocalPort 8080 -Action Allow

# 현재 활성화된 방화벽 규칙 확인
Get-NetFirewallRule | Where-Object { $_.Enabled -eq "True" -and $_.Direction -eq "Inbound" } |
    Select-Object DisplayName, Profile, Action |
    Format-Table -AutoSize

# 방화벽 규칙 삭제 (불필요할 때)
Remove-NetFirewallRule -DisplayName "DevServer 8080"
```

#### ⑤ 개발 서버 공유 (팀원이 내 PC의 개발 서버에 접속)

```powershell
# 내 PC의 현재 IP 주소 확인 (팀원에게 알려줄 IP)
(Get-NetIPAddress -AddressFamily IPv4 |
    Where-Object { $_.IPAddress -notmatch "^127\." -and $_.PrefixOrigin -ne "WellKnown" }
).IPAddress

# Python 개발 서버를 팀 전체에 오픈 (0.0.0.0 바인딩)
# python -m uvicorn main:app --host 0.0.0.0 --port 8000
# 팀원은 http://<위에서 확인한 내 IP>:8000 으로 접속

# Node.js 개발 서버 예시
# npx serve -l 3000 --host 0.0.0.0
```

#### ⑥ 네트워크 공유 설정 요약표

| 목적 | 방법 | 명령어 예시 |
|------|------|------------|
| 폴더 공유 (서버 측) | SMB 공유 생성 | `New-SmbShare -Name "TeamShare" -Path "C:\TeamShare" -FullAccess "Everyone"` |
| 폴더 접근 (클라이언트) | 네트워크 드라이브 매핑 | `net use Z: \\192.168.1.100\TeamShare` |
| 팀원 PC 검색 | Ping 스캔 | `Test-Connection -ComputerName 192.168.1.X -Count 1` |
| 포트 접근 확인 | TCP 연결 테스트 | `Test-NetConnection -ComputerName 192.168.1.100 -Port 8080` |
| 방화벽 허용 | 인바운드 규칙 추가 | `New-NetFirewallRule -LocalPort 8080 -Action Allow` |
| 개발 서버 공유 | 0.0.0.0 바인딩 | `uvicorn main:app --host 0.0.0.0 --port 8000` |



---

## 1) WSL 환경 구축 (Windows 사용자)

### 설치 목적
- Windows에서도 Linux 기반 개발 환경을 사용하기 위함
- Docker, Python, Node.js, Java CLI 도구를 일관된 방식으로 사용 가능

### 설치 순서
1. 관리자 권한 PowerShell 실행
2. 아래 명령어 실행

```powershell
wsl --install
```

3. 재부팅 후 Ubuntu 배포판 계정 생성
4. WSL 버전 확인

```powershell
wsl --status
wsl -l -v
```

### 공식 사이트
- https://learn.microsoft.com/windows/wsl/install

---

## 2) Python 다운로드 및 환경 구축

### 설치 순서 (Windows)
1. 공식 다운로드 페이지 접속
2. 최신 Python 3 설치 파일 다운로드
3. 설치 시 **Add Python to PATH** 체크 후 설치
4. 버전 확인

```bash
python --version
pip --version
```

### 동작 확인 (Hello World)
```bash
python -c "print('Hello, World!')"
```

예상 출력:
```
Hello, World!
```

### 권장 가상환경 생성

Python 프로젝트마다 독립적인 패키지 환경을 유지하기 위해 가상환경을 사용합니다.

#### venv (내장 모듈 — 가장 기본)
```bash
python -m venv .venv

# Windows PowerShell
.\.venv\Scripts\Activate.ps1

# macOS / Linux / WSL
source .venv/bin/activate

# 비활성화
deactivate
```

#### pyenv — 여러 Python 버전 관리 (macOS/Linux/WSL 권장)

pyenv 를 사용하면 프로젝트별로 다른 Python 버전을 사용할 수 있습니다.

```bash
# pyenv 설치 (Linux/WSL/macOS)
curl https://pyenv.run | bash

# 셸 설정 추가 (~/.bashrc 또는 ~/.zshrc)
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
source ~/.bashrc

# 특정 Python 버전 설치
pyenv install 3.12.4
pyenv install 3.11.9

# 전역 버전 설정
pyenv global 3.12.4

# 특정 프로젝트 디렉터리에만 버전 고정
cd my-project
pyenv local 3.11.9

# 설치된 버전 목록 확인
pyenv versions
```

#### conda / Miniconda — 데이터 분석·ML 환경에 적합

```bash
# Miniconda 설치 (Linux/WSL)
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/miniconda3
eval "$($HOME/miniconda3/bin/conda shell.bash hook)"
conda init

# 환경 생성 및 활성화
conda create -n myenv python=3.12
conda activate myenv

# 환경 목록 확인
conda env list

# 환경 삭제
conda remove -n myenv --all
```

---

### pip 기본 설정 및 패키지 관리

```bash
# pip 최신화 (항상 먼저 실행 권장)
pip install --upgrade pip

# 사내 또는 사설 PyPI 미러 설정 (Nexus 연동 등)
pip config set global.index-url http://<NEXUS-IP>:8081/repository/pypi-proxy/simple/
pip config set global.trusted-host <NEXUS-IP>

# 설치된 패키지 목록 저장 / 복원
pip freeze > requirements.txt
pip install -r requirements.txt

# 특정 패키지 설치 / 삭제
pip install requests fastapi uvicorn
pip uninstall requests

# 패키지 정보 확인
pip show requests
pip list --outdated
```

#### pyproject.toml 기반 현대적 프로젝트 구성 (PEP 518)

```bash
# pip 대신 uv (Rust 기반 초고속 패키지 관리자) 사용 권장
pip install uv

# 새 프로젝트 초기화
uv init my-project
cd my-project

# 패키지 추가 / 삭제
uv add fastapi uvicorn
uv remove requests

# 가상환경 생성 및 활성화
uv venv
source .venv/bin/activate

# pyproject.toml 기반 동기화
uv sync
```

---

### 코드 품질 도구 설치 및 설정

```bash
# 포매터 (코드 스타일 자동 정렬)
pip install black isort

# 린터 (코드 오류·스타일 검사)
pip install flake8 pylint

# 타입 검사
pip install mypy

# 통합 린터 (black + isort + flake8 대체)
pip install ruff

# 한 번에 설치
pip install black isort flake8 mypy ruff
```

**ruff 설정 예시** (`pyproject.toml`):

```toml
[tool.ruff]
line-length = 88
select = ["E", "F", "I", "N", "W"]
ignore = ["E501"]

[tool.black]
line-length = 88

[tool.isort]
profile = "black"
```

**실행 예시**:
```bash
# 코드 포매팅
black .
isort .

# 린트 검사
ruff check .
mypy src/

# 자동 수정
ruff check --fix .
```

---

### 테스트 환경 구성

```bash
# pytest 설치
pip install pytest pytest-cov

# 테스트 실행
pytest

# 커버리지 포함 실행
pytest --cov=src --cov-report=html

# 특정 파일/함수만 실행
pytest tests/test_main.py::test_hello -v
```

**테스트 파일 예시** (`tests/test_main.py`):

```python
def add(a: int, b: int) -> int:
    return a + b

def test_add():
    assert add(1, 2) == 3
    assert add(-1, 1) == 0
```

---

### VS Code Python 개발 환경 설정

**필수 확장(Extension) 설치**:

| 확장 이름 | 용도 |
|-----------|------|
| Python (Microsoft) | 기본 Python 지원 |
| Pylance | 타입 검사, IntelliSense |
| Black Formatter | 저장 시 자동 포매팅 |
| Ruff | 빠른 린터 통합 |
| Python Test Explorer | pytest GUI 실행 |

**`.vscode/settings.json` 권장 설정**:

```json
{
  "python.defaultInterpreterPath": "${workspaceFolder}/.venv/bin/python",
  "editor.formatOnSave": true,
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter"
  },
  "python.linting.enabled": true,
  "python.linting.ruffEnabled": true,
  "python.testing.pytestEnabled": true,
  "python.testing.pytestArgs": ["tests"]
}
```

---

### Python 개발 환경 구성 요약표

| 구성 요소 | 도구 | 역할 |
|-----------|------|------|
| 버전 관리 | pyenv | 여러 Python 버전 전환 |
| 가상환경 | venv / conda | 프로젝트별 패키지 격리 |
| 패키지 관리 | pip / uv | 패키지 설치·삭제·동기화 |
| 포매터 | black / ruff | 코드 스타일 자동 정렬 |
| 린터 | ruff / flake8 | 코드 오류 검사 |
| 타입 검사 | mypy | 정적 타입 분석 |
| 테스트 | pytest | 단위·통합 테스트 |
| IDE | VS Code + Pylance | 통합 개발 환경 |

### 공식 사이트
- https://www.python.org/downloads/
- https://github.com/pyenv/pyenv
- https://docs.conda.io/en/latest/miniconda.html
- https://github.com/astral-sh/uv
- https://github.com/astral-sh/ruff

---

## 2-1) Google Antigravity — Python Easter Egg

> **참고**: 여기서 다루는 "Antigravity"는 Python 표준 라이브러리에 숨겨진 이스터에그로, 구글이 2025년 11월 공개한 실제 AI 코딩 에이전트 IDE **"Google Antigravity"**와는 이름만 같을 뿐 관련이 없습니다. 실제 서비스 가입·사용법은 [2-5) Google Antigravity (AI 코딩 에이전트 IDE)](#2-5-google-antigravity-ai-코딩-에이전트-ide) 절을 참고하세요.

### 개요

`import antigravity`는 Python에 내장된 이스터 에그(Easter Egg)입니다.  
Python 2.7부터 표준 라이브러리에 포함되어 있으며, 실행하면 기본 브라우저가 열리고 유명한 xkcd 만화 [#353 — Python](https://xkcd.com/353/)으로 이동합니다.

만화의 핵심 메시지: *"파이썬을 배우면 마치 하늘을 날 수 있는 것처럼 느껴진다."*

### 별도 설치 없음

Python 설치 시 자동으로 포함됩니다. 추가 패키지 설치가 필요 없습니다.

### 실행 방법

```bash
python -c "import antigravity"
```

또는 Python 대화형 셸에서:

```python
>>> import antigravity
```

실행 시 기본 브라우저가 자동으로 열리고 아래 URL로 이동합니다:

```
https://xkcd.com/353/
```

### antigravity 모듈 소스 확인

```python
import antigravity, inspect
print(inspect.getsource(antigravity))
```

예상 출력 (핵심 부분):

```python
import webbrowser
import hashlib

webbrowser.open("https://xkcd.com/353/")

def geohash(latitude, longitude, datedow):
    '''Compute geohash() using the Munroe algorithm.
    https://xkcd.com/426/
    '''
    h = hashlib.md5(datedow).digest()
    ...
```

> **참고**: 모듈 안에는 xkcd 위치 해시 알고리즘(`geohash`)도 숨어 있습니다.

### 학습 포인트

| 항목 | 설명 |
|------|------|
| `webbrowser` 모듈 | Python 표준 라이브러리 — OS 기본 브라우저 제어 |
| `hashlib` 모듈 | MD5 등 해시 알고리즘 제공 |
| Easter Egg 전통 | Python 커뮤니티의 유머 코드 관행 |

### 다른 Python Easter Egg

```python
import this        # The Zen of Python (파이썬 설계 철학 19가지)
import __hello__   # "Hello world!" 출력
```

### 공식 참고
- xkcd #353: https://xkcd.com/353/
- CPython 소스: https://github.com/python/cpython/blob/main/Lib/antigravity.py

---

## 2-2) Google Colab (가장 추천)

> **설치 없이 1초 만에 Python을 시작할 수 있는 가장 쉬운 방법입니다.**

Google에서 제공하는 무료 클라우드 기반 서비스로, 웹 브라우저만 있으면 별도의 설치 없이 바로 Python Notebook을 실행할 수 있습니다.

### 장점

| 항목 | 내용 |
|------|------|
| 비용 | 구글 계정만 있으면 100% 무료 |
| 성능 | 컴퓨터 성능과 무관하게 구글 서버를 사용 (무료 GPU 제공) |
| 저장/공유 | 구글 드라이브와 연동되어 저장 및 공유가 매우 쉬움 |
| 설치 | 별도 설치 불필요 — 브라우저만 있으면 즉시 시작 |

### 시작하는 방법

1. 웹 브라우저에서 **Google Colab** 에 접속합니다.
   - https://colab.research.google.com
2. 구글 계정으로 로그인합니다.
3. **새 노트** 를 클릭하면 즉시 Python 코드를 작성하고 실행할 수 있습니다.

### 기본 사용 예시

```python
# 셀에 입력 후 Shift+Enter 로 실행
print("Hello, Google Colab!")

# 패키지 설치 (셀에서 직접 실행)
!pip install requests

# 구글 드라이브 마운트
from google.colab import drive
drive.mount('/content/drive')
```

### import antigravity 실행해보기

Colab에서도 Python Easter Egg를 바로 실행할 수 있습니다:

```python
import antigravity
```

> Colab 환경에서는 브라우저 팝업 차단으로 인해 새 탭이 열리지 않을 수 있으며, 이는 정상적인 동작입니다.

### 무료 GPU 사용 방법

1. 상단 메뉴 → **런타임** → **런타임 유형 변경**
2. 하드웨어 가속기: **T4 GPU** 선택
3. **저장** 클릭 후 런타임이 재시작되면 GPU 사용 가능

```python
# GPU 사용 확인
import torch
print(torch.cuda.is_available())   # True 이면 GPU 사용 중
```

### 공식 사이트
- https://colab.research.google.com
- https://colab.research.google.com/notebooks/intro.ipynb (튜토리얼)

---

## 2-3) Google AI Studio — Gemini 모델 직접 실습

> **설치 없이 Google Gemini 모델을 바로 사용할 수 있는 무료 AI 개발 플랫폼입니다.**

Google에서 제공하는 AI 개발자 도구로, 브라우저에서 Gemini 모델과 직접 대화하고 프롬프트를 테스트하며 코드를 생성할 수 있습니다.

### 장점

| 항목 | 내용 |
|------|------|
| 비용 | 구글 계정만 있으면 무료 사용 가능 (API 키 발급 포함) |
| 모델 | Gemini 2.0 Flash / Gemini 2.5 Pro 등 최신 모델 즉시 사용 |
| 기능 | 텍스트·이미지·오디오·영상 멀티모달 입력 지원 |
| API | API 키 발급 → Python/Node.js 코드에 바로 연동 가능 |
| 저장 | 프롬프트 저장 및 공유, 시스템 프롬프트 설정 |

### 시작하는 방법

1. 웹 브라우저에서 **Google AI Studio** 에 접속합니다.
   - https://aistudio.google.com/prompts/new_chat
2. 구글 계정으로 로그인합니다.
3. 상단에서 모델(예: **Gemini 2.0 Flash**)을 선택합니다.
4. 채팅창에 프롬프트를 입력하면 즉시 응답을 받을 수 있습니다.

### 기본 사용 예시

```
# 텍스트 프롬프트 예시
"Python으로 FastAPI 서버를 만드는 예제 코드를 작성해줘"

# 이미지 분석
이미지 파일을 드래그&드롭 → "이 이미지에 무엇이 있는지 설명해줘"

# 코드 디버깅
오류 메시지를 붙여넣기 → "이 오류의 원인과 해결 방법을 알려줘"
```

### API 키 발급 및 Python 연동

AI Studio에서 발급한 API 키로 코드에서 직접 Gemini를 호출할 수 있습니다.

```python
# 패키지 설치
# pip install google-generativeai

import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")  # AI Studio에서 발급한 키

model = genai.GenerativeModel("gemini-2.0-flash")
response = model.generate_content("안녕하세요! Python 학습에 대해 알려주세요.")
print(response.text)
```

### 시스템 프롬프트(System Instruction) 설정

```python
model = genai.GenerativeModel(
    model_name="gemini-2.0-flash",
    system_instruction="당신은 Python 전문가입니다. 항상 한국어로 답변하고 코드 예시를 포함하세요."
)
response = model.generate_content("FastAPI와 Flask의 차이점은?")
print(response.text)
```

### 멀티모달 사용 (이미지 분석)

```python
import google.generativeai as genai
from PIL import Image

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel("gemini-2.0-flash")

image = Image.open("diagram.png")
response = model.generate_content(["이 다이어그램을 설명해줘", image])
print(response.text)
```

### Google Colab과의 차이점

| 구분 | Google Colab | Google AI Studio |
|------|--------------|-----------------|
| 주 목적 | Python 코드 실행 환경 | AI 모델 프롬프트 테스트 |
| 실행 방식 | Jupyter Notebook | 채팅/프롬프트 인터페이스 |
| 모델 | 사용자가 직접 로드 | Gemini 모델 내장 |
| API 키 | 별도 설정 | AI Studio에서 바로 발급 |
| 무료 GPU | T4 GPU 제공 | 해당 없음 (모델 서버 측 실행) |

> **활용 팁**: AI Studio에서 프롬프트를 테스트한 뒤 → API 키를 발급받아 → Colab 또는 로컬에서 코드로 연동하는 흐름이 가장 효율적입니다.

### 학습 포인트

| 항목 | 설명 |
|------|------|
| 프롬프트 엔지니어링 | 시스템 프롬프트, Few-shot, Chain-of-thought 실습 |
| 멀티모달 AI | 텍스트·이미지·PDF·영상 복합 입력 처리 |
| API 연동 | `google-generativeai` SDK로 Python/Node.js 앱에 AI 통합 |
| 모델 비교 | Gemini 2.0 Flash(빠름) vs Gemini 2.5 Pro(정확) 성능 비교 |

### 공식 사이트
- https://aistudio.google.com/prompts/new_chat
- https://ai.google.dev/gemini-api/docs (Gemini API 문서)
- https://github.com/google-gemini/cookbook (예제 모음)

---

## 2-4) Google NotebookLM — 자료 기반 AI 리서치 도구

> **각종 자료·논문·보고서를 업로드하면 그 안의 내용만 근거로 답변하는 "출처 기반(source-grounded)" AI 노트 도구입니다.**

### 개요
NotebookLM은 업로드한 문서(소스)만을 근거로 요약·질의응답·오디오 요약(팟캐스트)·마인드맵 등을 생성합니다. 일반 챗봇과 달리 답변에 항상 **출처 인용(citation)**이 붙어 어느 문서·페이지에서 나온 내용인지 추적할 수 있어, 각종 자료 분석이나 논문 리뷰에 특히 유용합니다.

### 가입 및 접속
1. https://notebooklm.google.com 접속
2. 개인 Gmail 계정 또는 소속 Google Workspace 계정으로 로그인(별도 가입 절차 없음, Google 계정만 있으면 즉시 사용 가능)
3. 최초 접속 시 국가/약관 동의 화면 확인 후 진행

### 노트북(Notebook) 생성 및 소스 추가
1. 홈 화면 → **Create new notebook**(새 노트북 만들기)
2. **Add sources**에서 소스 업로드
   - 지원 형식: PDF, Google Docs/Slides, 웹사이트 URL, 텍스트 붙여넣기, YouTube 링크(자막 기반 분석), 오디오 파일
   - 노트북 1개당 다수의 소스를 업로드하고 동시에 근거로 활용 가능(소스 개수·용량은 요금제별 한도 존재)
3. 업로드 완료 후 자동으로 각 소스 요약이 생성됨

### 핵심 기능
| 기능 | 설명 |
|------|------|
| Chat(질의응답) | 업로드한 소스 내용만 근거로 답변, 답변마다 출처 인용 표시 |
| Audio Overview | 소스 내용을 두 명의 AI 진행자가 대화하는 팟캐스트 형태 오디오로 자동 생성(복습·이동 중 청취용) |
| Study Guide / FAQ / Timeline | 소스 기반 학습 가이드, 예상 질문, 사건/개념의 시간순 정리 자동 생성 |
| Mind Map | 소스 내용을 시각적 마인드맵으로 구조화 |
| Notes(노트) | AI 답변을 클릭 한 번으로 노트로 저장·편집 후 소스로 재활용 |
| 공유(Share) | 노트북을 다른 사용자와 공유해 함께 열람·질의(조직 계정 기준 권한 관리 가능) |

### 기본 사용 예시
```
# 소스 업로드 후 질의 예시
"이 자료에서 3장의 핵심 개념 3가지를 요약해줘 (출처 포함)"

# Audio Overview 생성
우측 패널 → [Audio Overview] → [Generate] 클릭 → 생성 완료 후 재생/다운로드

# 여러 소스 간 비교 질의
"업로드한 논문 2편의 실험 방법 차이를 표로 비교해줘"
```

### 무료(개인) vs Plus(유료) 한도 (가입 시점에 따라 변동될 수 있음 — 최신 값은 공식 요금 페이지에서 확인)
| 구분 | 개인(무료) | NotebookLM Plus |
|------|-----------|-----------------|
| 노트북 개수 | 제한된 개수 | 대폭 확대 |
| 소스 개수/노트북 | 제한된 개수 | 확대 |
| Audio Overview 생성 횟수 | 일일 제한 | 확대 + 커스터마이징(길이·언어·초점) |
| 공유/협업 | 제한적 | 조직 단위 공유·권한 관리 |

> Google Workspace / Google One AI Premium 구독에 NotebookLM Plus가 포함되는 경우가 있으므로, 이미 구독 중이라면 별도 결제 전 확인 권장.

### 학습 포인트
- 각종 자료를 올려 **수업 준비용 FAQ/타임라인 자동 생성**
- 학생에게 **Audio Overview(팟캐스트)** 링크를 공유해 복습 자료로 활용
- 여러 참고문헌을 동시에 업로드해 **선행 연구 비교표** 즉시 생성

### 공식 사이트
- https://notebooklm.google.com
- https://support.google.com/notebooklm (도움말)

---

## 2-5) Google Antigravity (AI 코딩 에이전트 IDE)

> **Gemini 3 기반, 구글이 2025년 11월 공개한 에이전트 우선(Agent-first) 코딩 IDE입니다. Cursor·Windsurf와 유사한 포지션의 독립 실행형 데스크톱 에디터입니다.**
> 위 2-1절의 Python `import antigravity` 이스터에그와는 이름만 같을 뿐 전혀 다른 제품입니다.

### 개요
Google Antigravity는 VS Code 계열 에디터를 기반으로 하되, 코드 작성뿐 아니라 **에이전트가 스스로 계획을 세우고, 파일을 수정하고, 터미널 명령을 실행하고, 브라우저로 결과를 직접 검증**하는 것까지 하나의 데스크톱 앱 안에서 처리하도록 설계되었습니다. Gemini 3 Pro를 기본 모델로 제공하며, 다른 주요 모델도 함께 선택할 수 있습니다.

### 설치 방법
1. https://antigravity.google 접속
2. OS에 맞는 설치 파일 다운로드
   - Windows: `.exe` 인스톨러
   - macOS: `.dmg` (Apple Silicon / Intel 별도 배포)
   - Linux: `.deb`/`.AppImage` 등(배포 형태는 업데이트될 수 있음)
3. 설치 후 실행 → 최초 실행 시 기존 VS Code 설정(테마·키바인딩·확장) 가져오기 여부 선택 가능

### 가입 및 로그인
1. 최초 실행 시 **Sign in with Google** 클릭
2. 개인 Gmail 계정으로 로그인(가입 절차 별도 없음 — Google 계정 보유 시 즉시 시작)
3. 로그인 완료 후 워크스페이스(프로젝트 폴더) 열기 — 기존 VS Code처럼 **Open Folder**로 로컬 저장소 지정

### 핵심 개념 및 화면 구성
| 구성 요소 | 설명 |
|-----------|------|
| Editor View | 기존 코드 에디터와 동일한 파일 편집 화면 |
| Agent Manager | 여러 개의 에이전트 작업을 동시에 생성·관리·모니터링하는 대시보드(백그라운드로 여러 작업 병렬 진행 가능) |
| Agent(에이전트) | 자연어 지시를 받아 계획 수립 → 파일 수정 → 명령 실행까지 자율 수행 |
| Browser 서브에이전트 | 에이전트가 로컬에서 실행 중인 웹앱을 직접 브라우저로 열어 동작을 확인·스크린샷 촬영 |
| Artifacts(아티팩트) | 에이전트의 작업 계획, 스크린샷, 실행 로그를 사람이 검토할 수 있도록 정리해 보여주는 패널 — 결과를 승인/반려하며 신뢰도 확보 |

### 기본 사용법
```
1. 좌측 Agent Manager → [New Agent] 클릭
2. 자연어로 작업 지시 입력
   예) "이 저장소의 lab01-python-app에 pytest 기반 유닛 테스트를 추가하고 실행해서 통과를 확인해줘"
3. 에이전트가 계획(Plan)을 먼저 제시 → 사용자가 검토 후 승인
4. 에이전트가 파일 수정·터미널 명령 실행·(필요 시) 브라우저로 결과 검증
5. Artifacts 패널에서 변경 diff·스크린샷·로그를 확인 후 최종 승인/반려
```

### 모델 선택
- 기본: **Gemini 3 Pro** (구글 계정 로그인만으로 별도 API 키 없이 사용 가능한 무료/포함 한도 제공)
- 설정에서 다른 모델로 전환 가능(제공 모델 목록은 지속적으로 업데이트되므로 IDE 내 모델 선택 메뉴에서 최신 목록 확인)

### 요금 및 이용 한도
- 공개 초기에는 무료로 제공되고 있으나, 사용량 한도·요금 정책은 정식 출시 이후 변경될 수 있으므로 **IDE 내 Billing/Usage 메뉴** 또는 공식 사이트에서 최신 정책을 확인하세요.

### VS Code와의 관계 — 확장·설정 이관
Antigravity는 VS Code 확장 생태계와 대부분 호환됩니다.
```bash
# 기존 VS Code 확장 목록 내보내기
code --list-extensions > extensions.txt

# Antigravity에서 동일 확장 설치 (Antigravity CLI가 등록된 경우)
# 각 항목을 Antigravity의 확장 마켓플레이스에서 검색해 설치
```

### 다른 에이전트 IDE와 비교
| 항목 | Google Antigravity | Cursor | Windsurf |
|------|---------------------|--------|----------|
| 기반 | VS Code 계열 | VS Code 계열 | VS Code 계열 |
| 기본 모델 | Gemini 3 Pro (멀티 모델 지원) | 멀티 모델(선택형) | 멀티 모델(선택형) |
| 특징 | Agent Manager로 다중 에이전트 병렬 관리, 브라우저 서브에이전트 내장 | 인라인 편집·Composer 중심 | Cascade 에이전트 흐름 중심 |
| 배포사 | Google | Anysphere | Cognition(구 Windsurf) |

### 학습 포인트
- **계획(Plan) 우선 승인 구조**: 에이전트가 실행 전 계획을 먼저 보여주므로, 대규모 변경 전 검토 습관을 들이기 좋음
- **Artifacts로 검증 가능한 자율성**: "믿고 맡기기"가 아니라 스크린샷·로그 기반으로 결과를 검증하는 워크플로우 학습
- 팀 프로젝트에서 반복 작업(테스트 추가, 리팩터링, 문서화)을 Agent Manager로 병렬 위임하는 방식 실습

### 공식 사이트
- https://antigravity.google
- https://blog.google (구글 공식 블로그 — 발표 아티클 검색)

---

## 3) Node.js 다운로드 및 환경 구축

### 설치 순서
1. 공식 페이지에서 LTS 버전 다운로드
2. 기본 옵션으로 설치
3. 버전 확인

```bash
node --version
npm --version
```

### 동작 확인 (Hello World)
```bash
node -e "console.log('Hello, World!')"
```

예상 출력:
```
Hello, World!
```

### npm 초기 설정 예시
```bash
npm config set init-author-name "your-name"
npm config set init-license "MIT"
```

### 공식 사이트
- https://nodejs.org/en/download

---

## 4) Docker 환경 구축

Docker 설치/호환성/장애조치 내용은 별도 폴더 문서로 분리했습니다.

- 문서 경로: [`docker-setup/README.md`](docker-setup/README.md)

### 빠른 설치 순서 (Docker Desktop 기준)
1. Docker Desktop 다운로드 및 설치
2. 설치 중 WSL2 연동 옵션 활성화
3. 설치 후 Docker Desktop 실행
4. 버전 확인

```bash
docker --version
docker compose version
```

### 동작 확인
```bash
docker run hello-world
```

### 공식 사이트
- https://www.docker.com/products/docker-desktop/

---

## 5) Java (OpenJDK) 설치 (요약)

> 상세 설치 가이드는 문서 맨 아래 **[부록: Java OpenJDK 상세 설치 가이드](#부록-java-openjdk-상세-설치-가이드-windows)** 를 참조하세요.

### 빠른 설치 요약

1. https://jdk.java.net/17/ 에서 Windows용 `.zip` 파일 다운로드
2. 압축 해제 후 `C:\jdk17` 경로로 이동
3. 시스템 환경 변수에 `JAVA_HOME=C:\jdk17` 추가, `Path`에 `%JAVA_HOME%\bin` 추가
4. 새 터미널에서 설치 확인

```bash
java --version
javac --version
```

### 공식 사이트
- https://jdk.java.net/ (OpenJDK Reference Implementation)

---

## 6) Git for Windows 설치

### 설치 목적
- 소스 코드 버전 관리 및 GitHub 연동

### 설치 순서
1. 아래 공식 사이트에서 최신 버전 다운로드
   - https://git-scm.com/download/win
2. **Click here to download the latest x64 version** 링크 클릭

![Git for Windows 다운로드 페이지](images/image-7.png)

3. 다운로드된 `.exe` 파일 실행 → UAC(사용자 계정 컨트롤) 허용 클릭

![Git 설치 UAC 허용](images/image-8.png)

4. 설치 마법사 기본 옵션 유지하며 진행
5. 설치 완료 후 버전 확인

```bash
git --version
```

---

## 7) Visual Studio Code (VS Code) 설치

### 설치 목적
- Java, Python, Node.js 등 다양한 언어를 지원하는 경량 IDE

### 설치 순서
1. 아래 공식 사이트 접속
   - https://code.visualstudio.com/download
2. 운영체제에 맞는 버전 선택 (Windows: **User Installer** 권장)

![VS Code 다운로드 페이지](images/image-9.png)

3. 다운로드된 설치 파일 실행 → 기본 옵션으로 설치
4. VS Code 실행 후 Java Extension Pack 설치 권장

### Java 프로젝트 실행 예시

VS Code 탐색기(Explorer) 패널에서 Java 소스 파일 구조를 확인하고 실행할 수 있습니다.

![VS Code Java 프로젝트 탐색기](images/image-10.png)

---

## 8) 필수 플랫폼 계정 준비 (Gmail · GitHub · Slack · Docker Hub · AWS · GCP)

### 8-1) Gmail 계정 가입 및 보안 설정
1. https://accounts.google.com/signup 접속 → Google 계정 생성
2. 휴대전화/복구 이메일 등록으로 계정 복구 수단 설정
3. Google 계정 관리 → **보안** → **2단계 인증** 활성화
4. 보안 알림/로그인 기기 내역을 주기적으로 확인
5. 교육용 서비스 가입 시 동일 Gmail 주소를 기준 계정으로 통일 권장

### 8-2) GitHub 가입 · 2FA · SSH/토큰 인증 · gh CLI 완전 가이드

#### A. 계정 가입
1. https://github.com 접속 → **Sign up**
2. 이메일 주소 입력 → 비밀번호 설정 → 사용자 이름(Username) 결정
   - Username은 프로필 URL(`github.com/사용자명`)이 되며 이후 변경 가능하지만 기존 링크가 깨질 수 있어 신중히 선택
3. 브라우저/이메일 인증 코드 확인(로봇 방지 퍼즐 포함될 수 있음)
4. 가입 설문(사용 목적 등) → **Free 플랜**으로 시작(개인 사용자는 대부분 무료 플랜으로 충분)
   - 조직 단위 협업이 필요하면 이후 **Settings → Organizations**에서 별도 조직(Organization) 생성 가능(무료 플랜도 조직 생성 가능, Team/Enterprise는 고급 권한관리·SSO 필요 시)
5. 프로필 설정 — **Settings → Public profile**에서 이름/소개/아바타/소속 입력

#### B. 2단계 인증(2FA) 설정 — 필수
1. 우측 상단 프로필 아이콘 → **Settings** → **Password and authentication**
2. **Two-factor authentication** → **Enable two-factor authentication**
3. 방식 선택
   - 권장: Authentication app(Google Authenticator, Authy 등 TOTP) — QR 코드 스캔 후 6자리 코드 입력
   - 대안: Security key(FIDO2/YubiKey), SMS(보안 취약 — 최후 수단)
4. **Recovery codes(복구 코드)** 다운로드 후 오프라인(비밀번호 관리자 등)에 안전하게 보관
5. 2FA 미설정 시 2026년 기준 GitHub 정책상 코드 기여(push) 자체가 제한될 수 있으므로 가입 직후 반드시 완료

#### C. SSH 키 생성 및 등록 (Git push/pull 인증)
```bash
# SSH 키 생성 (이미 있다면 생략)
ssh-keygen -t ed25519 -C "you@example.com"
# 저장 위치: 기본값(~/.ssh/id_ed25519) 그대로 Enter 권장

# SSH agent 등록
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# 공개키 복사 (아래 내용을 GitHub에 등록)
cat ~/.ssh/id_ed25519.pub
```
1. GitHub → **Settings** → **SSH and GPG keys** → **New SSH key**
2. Title(식별용 이름) 입력 → 위에서 복사한 공개키 붙여넣기 → **Add SSH key**
3. 연결 테스트
```bash
ssh -T git@github.com
# Hi <username>! You've successfully authenticated... 메시지 확인
```
4. 원격 저장소를 SSH 방식으로 설정
```bash
git remote set-url origin git@github.com:edumgt/edumgt-lab-init.git
```

#### D. Personal Access Token(PAT) 발급 (HTTPS 인증 · CI/CD · API 호출용)
GitHub는 2021년부터 비밀번호를 이용한 HTTPS Git 인증을 지원하지 않으므로, HTTPS로 push/pull 하거나 API를 호출하려면 토큰이 필요합니다.

1. **Settings** → **Developer settings** → **Personal access tokens**
2. **Fine-grained tokens**(권장) → **Generate new token**
   - Repository access: 특정 저장소만 선택(최소 권한 원칙)
   - Permissions: 필요한 항목만 체크(예: Contents: Read and write, Pull requests: Read and write)
   - Expiration: 90일 등 짧은 만료 기간 설정 권장
3. 또는 **Tokens (classic)** — 전체 계정 범위 스코프(`repo`, `workflow` 등) 필요 시 사용, 세분화가 안 되므로 최소한으로 사용
4. 생성된 토큰은 **최초 1회만 표시**되므로 즉시 안전한 곳에 저장

```bash
# HTTPS 인증 시 비밀번호 대신 토큰 입력
git clone https://github.com/edumgt/edumgt-lab-init.git
# Username: <github-username>
# Password: <발급받은 토큰 붙여넣기>

# 자격 증명 캐싱(재입력 방지)
git config --global credential.helper cache
```

#### E. GitHub CLI(gh) — 설치 및 인증
GitHub CLI를 사용하면 터미널에서 저장소·이슈·PR·Actions·시크릿 관리를 브라우저 전환 없이 처리할 수 있습니다. 전체 명령어는 아래 **["GitHub CLI (gh) 완전 명령어 가이드"](#github-cli-gh-완전-명령어-가이드)** 절에서 다루며, 여기서는 최초 설치·인증만 요약합니다.

```bash
# 설치 (Windows — winget)
winget install --id GitHub.cli

# 설치 (macOS — Homebrew)
brew install gh

# 설치 (Linux/WSL — Ubuntu)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update && sudo apt install gh

# 설치 확인
gh --version

# 인증 (대화형 — 브라우저 OAuth)
gh auth login
# ? What account do you want to log into? GitHub.com
# ? What is your preferred protocol for Git operations? HTTPS 또는 SSH
# ? Authenticate Git with your GitHub credentials? Yes
# ? How would you like to authenticate? Login with a web browser
#   → 표시되는 one-time code 복사 → 브라우저에서 붙여넣고 승인

# 인증 상태 확인
gh auth status

# 토큰 방식 인증(CI/비대화형 환경)
echo $GITHUB_TOKEN | gh auth login --with-token
```

#### F. 가입 후 보안 체크리스트
- [ ] 2FA(Authenticator 앱) 활성화 완료
- [ ] 복구 코드 오프라인 백업
- [ ] SSH 키 생성 및 GitHub에 등록, `ssh -T git@github.com` 성공 확인
- [ ] Fine-grained PAT 발급(필요 저장소·권한만 최소 부여, 만료 기간 설정)
- [ ] `gh auth login` 완료 및 `gh auth status`로 인증 확인
- [ ] 비밀번호 관리자에 PAT/복구 코드 저장(코드/저장소에는 절대 커밋 금지)

### 8-3) Slack 가입 및 워크스페이스 사용
1. https://slack.com/get-started 접속 → 계정 생성(또는 Google 계정으로 계속)
2. 초대 링크 또는 이메일 도메인으로 팀 워크스페이스 참여
3. 프로필 이름/사진/표시명 설정 후 본인 소개 업데이트
4. 필수 채널(`announcements`, `general`, `qna` 등) 우선 참여
5. 기본 사용법
   - 스레드(Thread)로 답글 작성해 대화 맥락 유지
   - 코드/로그는 코드 블록(백틱 3개)으로 공유
   - 멘션(`@here`, `@channel`)은 필요한 경우에만 사용
6. 알림 설정 최적화
   - 모바일/데스크톱 알림 시간대 설정
   - 중요 채널은 알림 유지, 기타 채널은 음소거 권장

### 8-4) Docker Hub 가입 및 2FA 설정
1. https://hub.docker.com 접속 → **Sign Up**으로 계정 생성
2. 이메일 인증 후 로그인
3. 우측 상단 계정 메뉴 → **Account Settings** → **Security**
4. **Two-factor authentication** 활성화 (Authenticator 앱 권장)
5. CLI 사용 시 토큰 기반 인증 권장

```bash
docker login -u <dockerhub-username>
```

### 8-5) AWS 가입 · 구독결제 · IAM · 프로젝트(계정) 구조 · 리전 · MFA · CLI 완전 가이드

#### A. 계정 가입 (Root Account 생성)
1. https://portal.aws.amazon.com/billing/signup 접속 → **Create an AWS Account**
2. 이메일 주소 + 계정 이름(회사명 또는 개인 식별명) 입력 → 인증 코드 확인
3. 루트 사용자 암호 설정 (다른 서비스와 절대 재사용하지 말 것)
4. 연락처 정보 입력 (개인/업무용 선택)
5. 결제 정보(신용/체크카드) 등록 → $1 내외 임시 승인 후 자동 취소(카드 유효성 검증용)
6. 전화번호 인증(SMS 또는 음성 코드)
7. 지원 플랜 선택 — 기본값 **Basic Support(무료)**로 충분 (Developer/Business는 유료 SLA 필요 시만 선택)
8. 가입 완료 후 https://console.aws.amazon.com 로그인 확인

> 가입 시 프로모션(Free Tier) 조건과 무료 크레딧 정책은 시점에 따라 달라질 수 있으므로, 가입 직전 공식 Free Tier 페이지(https://aws.amazon.com/free)에서 최신 조건을 반드시 재확인하세요.

#### B. 구독결제(Billing) 및 예산 알림 설정
1. 콘솔 우측 상단 계정명 → **Billing and Cost Management** 이동
2. **Payment preferences**에서 기본 결제 수단 확인/추가
3. **Budgets** → **Create budget** → 예산 유형(Cost budget) 선택 → 월 한도 금액 입력
4. 임계치(예: 50%, 80%, 100%) 도달 시 이메일 알림 수신자 등록
5. **Cost Explorer**로 서비스별/일자별 지출 추이 확인 (활성화 후 최대 24시간 반영 지연)
6. **Billing preferences** → PDF 인보이스 이메일 수신, 통화(Currency) 확인
7. (팀/조직 단위) **Consolidated Billing** — AWS Organizations로 여러 계정의 청구를 관리 계정 하나로 통합 가능

```bash
# CLI로 이번 달 비용 조회 예시
aws ce get-cost-and-usage \
  --time-period Start=2026-07-01,End=2026-07-24 \
  --granularity MONTHLY \
  --metrics "UnblendedCost"
```

#### C. 루트 계정 MFA 설정 (가입 직후 필수)
1. 콘솔 우측 상단 계정 메뉴 → **Security credentials**
2. **Multi-factor authentication (MFA)** → **Assign MFA device**
3. 디바이스 유형 선택
   - 권장: 가상 MFA 앱(Google Authenticator, Authy 등 TOTP)
   - 대안: 하드웨어 보안키(FIDO2/U2F), 하드웨어 OTP 토큰
4. QR 코드 스캔 후 연속된 인증 코드 2개 입력 → 등록 완료
5. 루트 계정은 이후 일상 작업(로그인)에 사용하지 않고, **결제·계정 설정 변경 등 최소한의 작업에만** 사용

#### D. IAM 사용자 · 그룹 · 역할 생성
루트 계정은 모든 권한을 가지므로 최초 설정 후에는 사용하지 않고, 관리자 권한을 가진 IAM 사용자를 만들어 사용합니다.

1. IAM 콘솔(https://console.aws.amazon.com/iam) → **User groups** → **Create group**
   - 그룹 이름: `Admins`
   - 정책 연결: `AdministratorAccess` (관리자) 또는 최소 권한 원칙에 따른 커스텀 정책
2. **Users** → **Create user**
   - 사용자 이름 입력 → **Provide user access to the AWS Management Console**(콘솔 로그인 필요 시 체크)
   - 방금 만든 `Admins` 그룹에 추가
3. 생성된 IAM 사용자로 재로그인 → 해당 사용자에도 **개별 MFA** 등록 (Security credentials 탭)
4. 프로그래밍 방식 접근(CLI/SDK)이 필요하면 **Security credentials** 탭 → **Access keys** → **Create access key**
   - Use case: *Command Line Interface (CLI)* 선택
   - 발급된 Access Key ID / Secret Access Key는 **최초 1회만 표시** — 반드시 안전한 곳에 저장(비밀번호 관리자 권장)
5. IAM 정책은 JSON 문서로 정의됩니다 (커스텀 최소 권한 정책 예시):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowS3ReadWriteOnSpecificBucket",
      "Effect": "Allow",
      "Action": ["s3:GetObject", "s3:PutObject", "s3:ListBucket"],
      "Resource": [
        "arn:aws:s3:::my-edumgt-bucket",
        "arn:aws:s3:::my-edumgt-bucket/*"
      ]
    }
  ]
}
```

```bash
# CLI로 관리자 그룹/사용자 생성 예시
aws iam create-group --group-name Admins
aws iam attach-group-policy --group-name Admins \
  --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
aws iam create-user --user-name alice
aws iam add-user-to-group --user-name alice --group-name Admins

# 액세스 키 발급 (JSON 형식으로 결과 확인)
aws iam create-access-key --user-name alice --output json
```

```json
{
  "AccessKey": {
    "UserName": "alice",
    "AccessKeyId": "AKIAIOSFODNN7EXAMPLE",
    "Status": "Active",
    "SecretAccessKey": "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
    "CreateDate": "2026-07-24T00:00:00+00:00"
  }
}
```

> **주의**: `SecretAccessKey`는 이 응답에서만 확인 가능하며 이후에는 재조회할 수 없습니다. 절대 Git 저장소에 커밋하지 마세요(본 문서의 "시크릿 스캐닝" 절 참고).

6. 여러 AWS 계정/조직 규모라면 장기 Access Key 대신 **IAM Identity Center**(구 AWS SSO)로 사람 사용자를 통합 인증하는 것을 권장 (임시 자격 증명 자동 발급·회전)

#### E. 프로젝트(계정) 구조 — AWS Organizations
AWS에는 GCP의 "프로젝트" 같은 리소스 컨테이너 개념이 없고, 대신 **계정(Account) 자체가 최상위 격리 단위**입니다. 여러 팀/환경(dev·staging·prod)을 분리하려면 AWS Organizations로 멀티 계정 구조를 구성합니다.

1. https://console.aws.amazon.com/organizations → **Create an organization**
2. 최초 계정이 **관리 계정(Management account)**이 됨
3. **Add an AWS account** → 신규 계정 생성 또는 기존 계정 초대
4. **Organizational Units(OU)** 생성 — 부서/환경별로 그룹화 (예: `Dev`, `Prod`, `Security`)
5. **Service Control Policies(SCP)**로 OU/계정 단위 최대 권한 범위 제한
6. **Consolidated Billing**으로 모든 멤버 계정의 청구를 관리 계정에서 통합 관리

#### F. 리전(Region) 설정
1. 콘솔 우측 상단 리전 드롭다운에서 작업 리전 선택 (예: **아시아 태평양(서울) `ap-northeast-2`**)
2. 대부분의 리소스는 리전 종속적이므로, 콘솔에서 리소스가 보이지 않으면 리전 선택부터 확인
3. CLI 기본 리전은 `aws configure` 또는 환경변수로 지정

```bash
# 사용 가능한 리전 목록 확인
aws ec2 describe-regions --output table

# 환경변수로 임시 지정
export AWS_DEFAULT_REGION=ap-northeast-2
```

#### G. AWS CLI 다운로드 및 설치 (v2)

```powershell
# Windows — MSI 인스톨러
# https://awscli.amazonaws.com/AWSCLIV2.msi 다운로드 후 실행
# 또는 winget 사용
winget install Amazon.AWSCLI
```

```bash
# macOS
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /

# 또는 Homebrew
brew install awscli
```

```bash
# Linux / WSL
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# 설치 확인
aws --version
```

#### H. AWS CLI 인증 설정
**방법 1 — Access Key 기반 (`aws configure`)**

```bash
aws configure
# AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
# AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
# Default region name [None]: ap-northeast-2
# Default output format [None]: json
```

위 명령은 아래 두 파일을 생성/수정합니다.

```ini
# ~/.aws/credentials
[default]
aws_access_key_id = AKIAIOSFODNN7EXAMPLE
aws_secret_access_key = wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY

# 여러 계정/역할을 쓸 경우 Named Profile 추가
[project-dev]
aws_access_key_id = AKIA...
aws_secret_access_key = ...
```

```ini
# ~/.aws/config
[default]
region = ap-northeast-2
output = json

[profile project-dev]
region = us-east-1
output = json
```

```bash
# 특정 프로파일로 명령 실행
aws s3 ls --profile project-dev

# 현재 인증 확인 (Access Key가 누구 소유인지 검증)
aws sts get-caller-identity
```

**방법 2 — IAM Identity Center(SSO) 기반 (조직/팀 단위 권장)**

```bash
aws configure sso
# SSO session name: my-sso
# SSO start URL: https://my-org.awsapps.com/start
# SSO region: ap-northeast-2
# → 브라우저가 열리고 로그인 후 계정/역할 선택
# CLI default client Region / output format 입력

# 이후 로그인/갱신
aws sso login --profile my-profile
```

**방법 3 — 임시 자격 증명(JSON 스키마)을 이용한 `credential_process` 연동**

AWS CLI는 외부 스크립트가 아래 JSON 형식을 표준출력으로 반환하면 이를 임시 자격 증명으로 사용할 수 있습니다(사내 Vault, STS AssumeRole 스크립트 등과 연동 시 유용).

```json
{
  "Version": 1,
  "AccessKeyId": "ASIAIOSFODNN7EXAMPLE",
  "SecretAccessKey": "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
  "SessionToken": "FQoGZXIvYXdzEDGA...EXAMPLE",
  "Expiration": "2026-07-24T12:00:00Z"
}
```

```ini
# ~/.aws/config
[profile vault-role]
credential_process = /usr/local/bin/get-temp-creds.sh
region = ap-northeast-2
```

#### I. AWS 접근 보안 체크리스트
- [ ] 루트 계정 MFA 등록 완료
- [ ] 루트 액세스 키는 생성하지 않음(원칙적으로 발급 자체를 지양)
- [ ] 관리자 IAM 사용자/그룹 별도 생성 및 MFA 등록
- [ ] 장기 Access Key 대신 IAM Identity Center 또는 IAM Role(AssumeRole) 우선 사용
- [ ] Access Key/Secret을 코드·Git에 절대 커밋하지 않음 (`.gitignore`, Secret Scanning 활용)
- [ ] 90일 이상 미사용 Access Key는 비활성화/삭제 (`aws iam list-access-keys`)

---

### 8-6) GCP(Google Cloud Platform) 가입 · 구독결제 · 프로젝트/조직 · IAM · 리전 · MFA · gcloud CLI 완전 가이드

#### A. 계정 가입
1. 기존 Gmail 계정으로 https://console.cloud.google.com 접속 (없다면 8-1 참고해 먼저 생성)
2. 최초 접속 시 국가/서비스 약관 동의
3. 처음 결제 계정을 만들 때 무료 체험(Free Trial) 안내가 표시될 수 있음(가입 시점별 크레딧 금액·기간은 변동되므로 https://cloud.google.com/free 에서 최신 조건 확인)
4. 조직 단위(회사) 사용 시에는 개인 Gmail 대신 **Google Workspace** 또는 무료 **Cloud Identity** 도메인 계정으로 가입하는 것을 권장(아래 C 참고)

#### B. 구독결제(Billing account) 설정
1. 콘솔 좌측 메뉴 → **Billing** → **Manage billing accounts**
2. **Create account**(신규) 또는 무료 체험 시 자동 생성된 계정 사용
3. 결제 수단(카드) 등록 → 본인 확인
4. 프로젝트를 만들면 **반드시 하나의 결제 계정과 연결**해야 유료 API/리소스 사용 가능
   - 콘솔: **Billing** → **Link a billing account** → 대상 프로젝트 선택
5. **Budgets & alerts** → **Create budget** → 프로젝트/결제계정 단위 월 예산과 알림 임계치(%) 설정
6. (고급) **Billing export**로 BigQuery에 상세 사용량 내보내기 → 세부 비용 분석

```bash
# 결제 계정 목록 확인
gcloud billing accounts list

# 프로젝트에 결제 계정 연결
gcloud billing projects link my-project-id \
  --billing-account=XXXXXX-XXXXXX-XXXXXX
```

#### C. 프로젝트 생성 및 조직(Organization) 구조 — GCP의 "테넌트" 개념
GCP는 AWS의 계정과 달리 **Project**가 리소스의 기본 컨테이너입니다. 여러 프로젝트를 하나의 조직으로 묶으려면 Google Workspace/Cloud Identity 도메인이 필요합니다.

**계층 구조**: `Organization(도메인)` → `Folder(선택, 부서/팀 단위)` → `Project` → `개별 리소스(VM, 버킷 등)`

1. 콘솔 상단 프로젝트 선택기 → **New Project**
   - Project name 입력 (표시용 이름, 변경 가능)
   - Project ID 확인/수정 — **전역 고유값이며 생성 후 변경 불가** (예: `edumgt-prod-2026`)
   - Location(조직/폴더) 선택 — 도메인 조직이 없으면 "No organization"으로 생성됨
2. 도메인 기반 조직이 필요한 경우
   - https://workspace.google.com 또는 무료 Cloud Identity(https://cloud.google.com/identity) 로 도메인 인증
   - 도메인 인증 완료 시 GCP가 자동으로 최상위 **Organization** 리소스를 생성
   - **IAM & Admin** → **Manage Resources**에서 Folder 생성 → 프로젝트를 Folder 하위로 이동
3. 조직이 없는 개인 프로젝트는 계층 최상단이 Project 자체가 됨(orphan project)

```bash
# 프로젝트 생성 (조직 하위)
gcloud projects create edumgt-prod-2026 \
  --name="EduMgt Production" \
  --organization=123456789012

# 현재 활성 프로젝트 확인/전환
gcloud config set project edumgt-prod-2026
gcloud config get-value project

# 조직/폴더 구조 조회
gcloud organizations list
gcloud resource-manager folders list --organization=123456789012
```

#### D. IAM 설정 (Principal · Role · Policy)
1. 콘솔 → **IAM & Admin** → **IAM**
2. **Grant Access** → Principal(구성원) 입력
   - Google 계정(개인 사용자), Google 그룹, 서비스 계정, Cloud Identity 도메인 전체 중 선택
   - `allUsers`/`allAuthenticatedUsers`(전체 공개)는 특별한 경우가 아니면 사용 금지
3. Role(역할) 선택
   - **기본 역할(Basic role)**: Owner/Editor/Viewer — 범위가 넓어 운영 환경에서는 지양
   - **사전 정의 역할(Predefined role)**: 서비스 단위 세분화 (예: `roles/storage.objectViewer`)
   - **커스텀 역할(Custom role)**: 필요한 권한만 조합해 최소 권한 원칙 구현
4. IAM 정책은 내부적으로 JSON/YAML 바인딩 문서로 관리되며 CLI로 직접 조회·수정 가능

```bash
# 프로젝트에 역할 부여 (CLI)
gcloud projects add-iam-policy-binding edumgt-prod-2026 \
  --member="user:alice@example.com" \
  --role="roles/editor"

# 현재 IAM 정책을 JSON으로 내보내기 → 수정 → 다시 적용
gcloud projects get-iam-policy edumgt-prod-2026 --format=json > policy.json
# (policy.json 편집 후)
gcloud projects set-iam-policy edumgt-prod-2026 policy.json
```

```json
{
  "bindings": [
    {
      "role": "roles/editor",
      "members": ["user:alice@example.com"]
    },
    {
      "role": "roles/storage.objectViewer",
      "members": ["serviceAccount:ci-bot@edumgt-prod-2026.iam.gserviceaccount.com"]
    }
  ],
  "etag": "BwXhqLp1Zz4=",
  "version": 1
}
```

#### E. 리전(Region) / 존(Zone) 설정
1. 리소스 생성 화면(Compute Engine, GKE 등)에서 개별적으로 Region/Zone 선택 가능
2. 서울 리전: `asia-northeast3` (존: `asia-northeast3-a/b/c`) — 지연시간 최소화를 위해 최우선 고려
3. CLI 기본값 지정

```bash
gcloud config set compute/region asia-northeast3
gcloud config set compute/zone asia-northeast3-a

# 사용 가능한 리전/존 목록
gcloud compute regions list
gcloud compute zones list --filter="region:asia-northeast3"
```

#### F. MFA(2단계 인증) 설정
GCP 콘솔 로그인은 Google 계정 인증을 그대로 사용하므로, MFA는 **Google 계정 보안 설정**에서 관리합니다.

1. https://myaccount.google.com/security 접속
2. **2단계 인증(2-Step Verification)** → 사용 설정
   - 권장: Google 프롬프트(스마트폰 승인) 또는 Authenticator 앱(TOTP)
   - 추가 옵션: 보안 키(FIDO2/YubiKey) — 관리자 계정에는 하드웨어 키 권장
3. 조직(Workspace/Cloud Identity) 전체에 강제 적용하려면
   - https://admin.google.com → **보안** → **2단계 인증**
   - 조직 단위(OU)별로 **적용(Enforce)** 설정 → 유예 기간 설정 후 전체 강제

#### G. gcloud CLI 다운로드 및 설치

```powershell
# Windows — 설치 프로그램 또는 winget
winget install Google.CloudSDK
```

```bash
# macOS — Homebrew
brew install --cask google-cloud-sdk

# 또는 공식 설치 스크립트 (macOS/Linux/WSL 공통)
curl https://sdk.cloud.google.com | bash
exec -l $SHELL
```

```bash
# Linux(Debian/Ubuntu) — apt 저장소 등록 방식
sudo apt-get update && sudo apt-get install -y apt-transport-https ca-certificates gnupg curl
curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | \
  sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | \
  sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
sudo apt-get update && sudo apt-get install -y google-cloud-cli

# 설치 확인
gcloud version
```

#### H. gcloud CLI 인증 및 초기 설정

```bash
# 최초 1회 대화형 초기 설정
# → 브라우저에서 Google 계정 로그인 → 사용할 프로젝트 선택 → 기본 region/zone 설정
gcloud init
```

```bash
# 사람 사용자 로그인 (gcloud 명령 실행용 인증)
gcloud auth login

# 애플리케이션 기본 자격 증명(ADC) 로그인
# → SDK/클라이언트 라이브러리(Python, Node 등)가 이 자격 증명을 자동으로 사용
gcloud auth application-default login
# 저장 위치: ~/.config/gcloud/application_default_credentials.json (Windows: %APPDATA%\gcloud\...)

# 현재 인증/설정 상태 확인
gcloud auth list
gcloud config list
```

```bash
# 여러 프로젝트/계정을 전환하며 사용할 때 — Named Configuration (AWS Named Profile과 유사)
gcloud config configurations create dev-config
gcloud config configurations activate dev-config
gcloud config set project edumgt-dev-2026
gcloud config set account alice@example.com

gcloud config configurations list
```

#### I. 서비스 계정(Service Account) 및 JSON 키 발급
사람이 아닌 애플리케이션/CI 파이프라인이 GCP API를 호출할 때는 서비스 계정을 사용합니다.

1. 콘솔 → **IAM & Admin** → **Service Accounts** → **Create Service Account**
2. 이름/설명 입력 → 필요한 역할만 최소로 부여(예: `roles/storage.objectAdmin`)
3. 생성된 서비스 계정 클릭 → **Keys** 탭 → **Add Key** → **Create new key** → **JSON** 선택
4. `프로젝트ID-서비스계정이름.json` 형태의 키 파일이 자동 다운로드됨 (아래는 예시 구조)

```json
{
  "type": "service_account",
  "project_id": "edumgt-prod-2026",
  "private_key_id": "a1b2c3d4e5f6...",
  "private_key": "-----BEGIN PRIVATE KEY-----\nMIIEvQ...\n-----END PRIVATE KEY-----\n",
  "client_email": "ci-bot@edumgt-prod-2026.iam.gserviceaccount.com",
  "client_id": "112233445566778899000",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "universe_domain": "googleapis.com"
}
```

```bash
# CLI로 서비스 계정/키 생성
gcloud iam service-accounts create ci-bot \
  --display-name="CI/CD Bot"

gcloud projects add-iam-policy-binding edumgt-prod-2026 \
  --member="serviceAccount:ci-bot@edumgt-prod-2026.iam.gserviceaccount.com" \
  --role="roles/storage.objectAdmin"

gcloud iam service-accounts keys create key.json \
  --iam-account=ci-bot@edumgt-prod-2026.iam.gserviceaccount.com
```

```bash
# JSON 키 파일을 이용한 인증 방법 (택 1)

# 방법 1 — 환경변수로 SDK/클라이언트 라이브러리에 자동 인식시키기
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/key.json"

# 방법 2 — gcloud CLI 자체를 서비스 계정으로 인증
gcloud auth activate-service-account \
  --key-file=/path/to/key.json
```

**서비스 계정 키 보안 체크리스트**
- [ ] JSON 키 파일은 `.gitignore`에 등록하고 절대 저장소에 커밋하지 않음
- [ ] 키 파일은 필요한 실행 환경에만 배포 (CI 시크릿 저장소 활용 — GitHub Actions Secrets 등)
- [ ] 미사용/오래된 키는 주기적으로 삭제 (`gcloud iam service-accounts keys list/delete`)
- [ ] 가능하면 장기 JSON 키 대신 **Workload Identity Federation**(키리스 연동, 예: GitHub Actions ↔ GCP)을 우선 검토
- [ ] 서비스 계정에도 프로젝트 전체가 아닌 최소 범위 역할만 부여

```bash
# 서비스 계정 키 조회/삭제 예시
gcloud iam service-accounts keys list \
  --iam-account=ci-bot@edumgt-prod-2026.iam.gserviceaccount.com

gcloud iam service-accounts keys delete KEY_ID \
  --iam-account=ci-bot@edumgt-prod-2026.iam.gserviceaccount.com
```

### 8-6-1) AWS ↔ GCP 핵심 개념 대응표

| 개념 | AWS | GCP |
|------|-----|-----|
| 최상위 리소스 컨테이너 | Account(계정) | Project(프로젝트) |
| 조직/테넌트 단위 | AWS Organizations (관리 계정 + 멤버 계정) | Organization (Workspace/Cloud Identity 도메인 필요) |
| 그룹화 단위 | OU(Organizational Unit) | Folder |
| 접근 제어 | IAM Users/Groups/Roles + JSON Policy | IAM Principals + Role Binding(JSON/YAML) |
| 사람 로그인 MFA | IAM → Security credentials → MFA 디바이스 | Google 계정 → 2단계 인증(myaccount.google.com) |
| 워크로드 인증 수단 | Access Key(ID+Secret) / IAM Role | 서비스 계정 JSON 키 / Workload Identity |
| CLI 최초 설정 | `aws configure` | `gcloud init` |
| CLI 인증 파일 위치 | `~/.aws/credentials`, `~/.aws/config` | `~/.config/gcloud/`, `application_default_credentials.json` |
| SSO/연합 인증 | IAM Identity Center | Workload Identity Federation |
| 결제 단위 | Billing(계정 단위, Organizations로 통합 가능) | Billing account(프로젝트에 연결) |
| 서울 리전 코드 | `ap-northeast-2` | `asia-northeast3` |

---

### 8-7) 사전 점검 체크리스트
- [ ] Gmail 계정 생성 및 2단계 인증 활성화
- [ ] GitHub 계정 생성 및 2FA 활성화
- [ ] Slack 계정 생성 및 팀 워크스페이스 참여
- [ ] Docker Hub 계정 생성 및 2FA 활성화
- [ ] AWS 계정 생성 및 루트 MFA 활성화
- [ ] AWS 관리자 IAM 사용자 생성 + MFA 등록 + Access Key 발급
- [ ] AWS CLI 설치 및 `aws configure`(또는 SSO) 인증 완료
- [ ] GCP 프로젝트 생성 및 결제 계정 연결
- [ ] GCP IAM 최소 권한 역할 부여 확인
- [ ] gcloud CLI 설치 및 `gcloud init` 인증 완료
- [ ] GCP 서비스 계정 JSON 키 발급 시 `.gitignore` 등록 확인
- [ ] 복구 코드/백업 코드 오프라인 보관

### 8-8) Git · GitHub 실무 사용 가이드 (브랜치 · 머지 · PR · Fork · 공개범위 · Settings)

#### A. 기본 Git 초기 설정
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --global core.autocrlf true   # Windows 권장
```

```bash
# 현재 설정 확인
git config --list
```

#### B. 브랜치 전략 (권장)
- `main`: 배포 가능한 안정 브랜치
- `develop`(선택): 통합 개발 브랜치
- `feature/*`: 기능 개발
- `fix/*` 또는 `hotfix/*`: 버그 수정
- `docs/*`: 문서 변경

브랜치 생성/이동:
```bash
git checkout -b feature/login-api
# 또는
git switch -c feature/login-api
```

작업 후 원격 반영:
```bash
git add .
git commit -m "feat: add login api"
git push -u origin feature/login-api
```

#### C. Merge 방법 정리
GitHub PR 머지 방식은 보통 3가지입니다.

1. **Create a merge commit**
   - 모든 커밋 이력을 그대로 유지
   - 협업 이력 추적이 쉬움
2. **Squash and merge**
   - 여러 커밋을 1개로 합쳐 `main` 히스토리를 깔끔하게 유지
   - 작은 단위 커밋이 많은 팀에 권장
3. **Rebase and merge**
   - 머지 커밋 없이 직선 히스토리 유지
   - 커밋 순서/의미를 유지하고 싶은 경우 사용

로컬에서 충돌 해결 + 병합 예시:
```bash
git checkout main
git pull origin main
git checkout feature/login-api
git merge main
# 충돌 해결 후
git add .
git commit
git push
```

#### D. Pull Request(PR) 표준 절차
1. 작업 브랜치에서 기능 구현 + 테스트 완료
2. 최신 `main` 반영(merge 또는 rebase) 후 충돌 해결
3. 원격 브랜치 push
4. GitHub에서 **Compare & pull request** 클릭
5. PR 템플릿 기준으로 목적/변경점/테스트 결과 작성
6. 리뷰어 지정(Assignees/Reviewers), 라벨(Label), 이슈 연결
7. CI 통과 + 리뷰 승인 후 머지
8. 머지 후 작업 브랜치 삭제

PR 제목 예시:
- `feat: 사용자 로그인 API 추가`
- `fix: 주문 조회 시 NPE 오류 수정`
- `docs: GitHub 운영 가이드 보강`

#### E. GitHub Forking 워크플로우 (오픈소스 기여 시 필수)
1. 원본 저장소(Upstream)를 GitHub에서 **Fork**
2. 내 계정의 Fork 저장소를 로컬에 clone
3. `upstream` 원격 추가

```bash
git clone https://github.com/<my-id>/<fork-repo>.git
cd <fork-repo>
git remote add upstream https://github.com/<org-or-owner>/<original-repo>.git
git remote -v
```

4. 기능 브랜치 생성 후 작업/커밋/push
5. 내 Fork 저장소에서 원본 저장소로 PR 생성

Upstream 동기화:
```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

#### F. Public / Private 저장소 사용 기준
| 구분 | Public 저장소 | Private 저장소 |
|------|---------------|----------------|
| 가시성 | 누구나 코드 열람 가능 | 권한 있는 사용자만 접근 |
| 권장 용도 | 오픈소스, 포트폴리오, 공개 학습 자료 | 사내 코드, 과제/시험, 고객 데이터 포함 프로젝트 |
| 주의사항 | 비밀정보 절대 커밋 금지 | 멤버 권한 최소화 원칙 적용 |

공통 보안 원칙:
- 토큰/비밀번호/API 키는 코드에 직접 저장하지 않기
- `.env`, 인증서, 키 파일은 `.gitignore`에 등록
- Secret Scanning / Dependabot / Code Scanning 활성화

#### G. GitHub Settings 핵심 설정 체크리스트
**(1) 개인 계정 Settings**
- **Password and authentication**: 2FA 필수
- **SSH and GPG keys**: SSH 키 등록 후 비밀번호 없는 안전한 push
- **Notifications**: 메일/웹 알림 최적화
- **Developer settings → Personal access tokens**: 최소 권한 토큰 발급

**(2) 저장소 Settings**
- **General**
  - 기본 브랜치(`main`) 확인
  - 템플릿(이슈/PR) 적용
- **Collaborators and teams**
  - 필요한 사용자만 최소 권한 부여
- **Branches / Rulesets**
  - `main` 보호 규칙 설정:
    - PR 필수
    - 최소 1명 이상 리뷰 승인
    - 상태 체크(CI) 통과 필수
    - 강제 푸시 금지
    - 브랜치 삭제/직접 푸시 제한
- **Security**
  - Dependabot alerts / updates 활성화
  - Secret scanning 활성화
  - Code scanning(CodeQL 등) 활성화
- **Actions**
  - 허용 액션 범위(Organization/Marketplace/Local) 정책 설정
  - 외부 PR에 대한 워크플로우 실행 정책 점검

**(3) 조직(Organization) Settings**
- SSO, 멤버십 승인 정책, 저장소 생성 권한 제한
- 팀 단위 권한 관리(Read/Triage/Write/Maintain/Admin)
- 감사 로그(Audit log) 주기적 점검

#### H. 팀 운영 시 권장 규칙 요약
- 기능 개발은 항상 브랜치에서 진행 (`main` 직접 작업 금지)
- PR 단위로 코드 리뷰 후 머지
- 머지 방식은 팀 규칙으로 통일 (예: 기본 `Squash and merge`)
- 이슈 번호를 커밋/PR에 연결 (`fixes #123`)
- 월 1회 이상 Settings/권한/보안 경고 점검

---

## 9) VirtualBox 설치 및 VM 네트워크 설정 (Windows)

### 설치 목적
- Windows PC에서 가상 머신(VM)을 실행하여 Linux 등 다양한 OS를 실습
- NAT 및 호스트 전용 어댑터(Host-Only Adapter) 구성을 통해 인터넷 및 내부 네트워크 사용

### 9-1) VirtualBox 다운로드 및 설치
1. 아래 공식 사이트에서 Windows용 설치 파일 다운로드
   - https://www.virtualbox.org/wiki/Downloads
2. 다운로드된 `.exe` 파일 실행 → 설치 마법사 기본 옵션 유지하며 진행
3. 설치 완료 후 **VirtualBox** 바탕화면 아이콘 또는 시작 메뉴에서 실행

### 9-2) VirtualBox 실행 및 VM 생성
1. VirtualBox Manager 화면에서 **새로 만들기(New)** 클릭
2. VM 이름, 운영체제 종류, 버전 선택 후 메모리·디스크 용량 설정
3. ISO 이미지를 마운트하여 OS 설치 완료

### 9-3) NAT 네트워크 설정
> NAT(Network Address Translation)를 사용하면 VM이 호스트 PC의 인터넷 연결을 공유합니다.

1. VM 목록에서 해당 VM 선택 → **설정(Settings)** → **네트워크(Network)**
2. **어댑터 1(Adapter 1)** 탭 선택
3. **다음에 연결됨(Attached to)** 드롭다운을 **NAT** 로 선택
4. **확인(OK)** 저장 후 VM 시작

| 항목 | 값 |
|------|-----|
| 연결 유형 | NAT |
| 어댑터 종류 | Intel PRO/1000 MT Desktop (기본값) |
| 프로미스큐어스 모드 | 거부 (기본값) |

### 9-4) 인터넷 사용 NIC 설정 확인 (VM 내부)
VM을 부팅한 후 VM 내부 터미널에서 네트워크 인터페이스를 확인합니다.

```bash
# IP 주소 확인 (Linux VM 내부)
ip addr show
# 또는
ifconfig
```

NAT 구성 시 VM은 일반적으로 `10.0.2.15` 대역의 IP를 받으며, 게이트웨이는 `10.0.2.2` 입니다.

### 9-5) Windows 호스트 PC에서 ipconfig 확인
VirtualBox를 설치하면 Windows 호스트에 **VirtualBox Host-Only Ethernet Adapter** 가상 NIC가 추가됩니다.

```powershell
ipconfig /all
```

아래와 유사한 항목이 새로 추가된 것을 확인할 수 있습니다.

```
VirtualBox Host-Only Network:
   Connection-specific DNS Suffix  . :
   IPv4 Address. . . . . . . . . . . : 192.168.56.1
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . :
```

---

## 10) VMware Workstation Player 설치 및 VM 네트워크 설정 (Windows)

### 설치 목적
- Windows PC에서 VMware 기반 가상 머신을 실행하여 Linux 등 다양한 OS 실습
- NAT 설정을 통해 VM에서 인터넷 접속 가능

### 10-1) VMware Workstation Player 다운로드 및 설치
1. 아래 공식 사이트에서 Windows용 무료 버전(Workstation Player) 다운로드
   - https://www.vmware.com/products/workstation-player.html
   - 또는 Broadcom Developer Portal: https://developer.broadcom.com/tools/vmware-workstation-player
2. 다운로드된 `.exe` 파일 실행 → 설치 마법사 기본 옵션 유지하며 진행
3. 설치 완료 후 **VMware Workstation Player** 실행

### 10-2) VMware 실행 및 VM 생성
1. VMware 메인 화면에서 **Create a New Virtual Machine** 클릭
2. ISO 이미지 선택 또는 **나중에 OS 설치(Install operating system later)** 선택
3. 게스트 OS 종류, 이름, 디스크 크기 설정 후 **Finish**

### 10-3) NAT 네트워크 설정
> VMware의 NAT 설정은 `VMnet8` 가상 스위치를 통해 VM이 호스트 PC의 인터넷을 공유합니다.

1. VM 목록에서 해당 VM 선택 → **Edit virtual machine settings** 클릭
2. **Network Adapter** 선택
3. **Network connection** 항목에서 **NAT: Used to share the host's IP address** 선택
4. **OK** 저장 후 VM 시작

| 항목 | 값 |
|------|-----|
| 연결 유형 | NAT (VMnet8) |
| 기본 서브넷 | 192.168.157.0/24 (VMware 설치 시 자동 할당) |
| 게이트웨이 IP | 192.168.157.2 |

### 10-4) 인터넷 사용 NIC 설정 확인 (VM 내부)
VM을 부팅한 후 VM 내부 터미널에서 네트워크 인터페이스를 확인합니다.

```bash
# IP 주소 확인 (Linux VM 내부)
ip addr show
# 또는
ifconfig

# 인터넷 연결 확인
ping -c 4 8.8.8.8
```

NAT 구성 시 VM은 VMnet8 서브넷 대역(예: `192.168.157.x`)의 IP를 DHCP로 할당받습니다.

### 10-5) Windows 호스트 PC에서 ipconfig 확인
VMware를 설치하면 Windows 호스트에 **VMware Network Adapter VMnet1** (Host-Only) 및 **VMware Network Adapter VMnet8** (NAT) 가상 NIC 2개가 추가됩니다.

```powershell
ipconfig /all
```

아래와 유사한 항목 2개가 새로 추가된 것을 확인할 수 있습니다.

```
VMware Network Adapter VMnet1 (Host-Only):
   IPv4 Address. . . . . . . . . . . : 192.168.116.1
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . :

VMware Network Adapter VMnet8 (NAT):
   IPv4 Address. . . . . . . . . . . : 192.168.157.1
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . :
```

---

## 11) VirtualBox vs VMware: Windows ipconfig 비교

VirtualBox와 VMware를 모두 설치하면 Windows의 `ipconfig` 결과에 아래와 같은 가상 NIC들이 추가됩니다.

| 가상화 소프트웨어 | 추가되는 NIC 이름 | 용도 | 기본 IP 대역 |
|---|---|---|---|
| VirtualBox | VirtualBox Host-Only Ethernet Adapter | 호스트 ↔ VM 통신 | 192.168.56.0/24 |
| VMware | VMware Network Adapter VMnet1 | Host-Only (호스트 ↔ VM) | 192.168.116.0/24 |
| VMware | VMware Network Adapter VMnet8 | NAT (VM 인터넷 공유) | 192.168.157.0/24 |

### ipconfig 실행 예시

```powershell
# Windows PowerShell 또는 명령 프롬프트(cmd)에서 실행
ipconfig /all
```

```
이더넷 어댑터 VirtualBox Host-Only Network:
   연결별 DNS 접미사 . . . . :
   IPv4 주소 . . . . . . . . . . . . : 192.168.56.1
   서브넷 마스크 . . . . . . . . . . : 255.255.255.0
   기본 게이트웨이 . . . . . . . . . :

이더넷 어댑터 VMware Network Adapter VMnet1:
   연결별 DNS 접미사 . . . . :
   IPv4 주소 . . . . . . . . . . . . : 192.168.116.1
   서브넷 마스크 . . . . . . . . . . : 255.255.255.0
   기본 게이트웨이 . . . . . . . . . :

이더넷 어댑터 VMware Network Adapter VMnet8:
   연결별 DNS 접미사 . . . . :
   IPv4 주소 . . . . . . . . . . . . : 192.168.157.1
   서브넷 마스크 . . . . . . . . . . : 255.255.255.0
   기본 게이트웨이 . . . . . . . . . :
```

> **참고**: 위 IP 주소는 소프트웨어 설치 시 자동으로 할당되며 환경에 따라 다를 수 있습니다.

---

---

## 25. 최종 추천 아키텍처

### 목표 환경

| 항목 | 구성 |
|------|------|
| 호스트 OS | Windows PC |
| 가상화 | VMware Workstation (Player/Pro) |
| 게스트 OS | Ubuntu 22.04 / 24.04 |
| Kubernetes | 단일 노드 (kubeadm) |
| 운영 서비스 | Harbor · Nexus · Jupyter |
| 외부 노출 | MetalLB + NGINX Ingress |

### 개발/테스트 환경 권장 구성

| 항목 | 권장 값 |
|------|---------|
| VMware 네트워크 | Bridged (권장) 또는 NAT |
| Ingress Controller | NGINX Ingress |
| LoadBalancer 구현 | MetalLB |
| 이름 해석 | Windows hosts 파일 |

### 운영/사내망 환경 권장 구성

| 항목 | 권장 값 |
|------|---------|
| 가상화 플랫폼 | VMware 또는 KVM/Proxmox |
| Ingress Controller | NGINX Ingress |
| LoadBalancer 구현 | MetalLB |
| 이름 해석 | 사내 DNS |

### 접속 흐름

```
사용자 브라우저
  ↓
web.test.com / jup.test.com / harbor.test.com / nexus.test.com
  ↓
hosts 파일 또는 사내 DNS
  ↓
MetalLB IP  (예: 192.168.253.200)
  ↓
NGINX Ingress Controller
  ↓
ClusterIP Service
  ↓
Pod
```

### 핵심 구성 요소 요약

| 구성 요소 | 역할 |
|-----------|------|
| VMnet1 | Host-only — 내부 테스트 전용 |
| VMnet8 | NAT — 인터넷/개발용 |
| Bridged | 실제 네트워크 연결 — 운영형에 적합 |
| Pod IP (`10.244.x.x`) | Kubernetes 내부 전용 |
| ClusterIP (`10.96.x.x`) | 클러스터 내부 서비스 통신용 |
| MetalLB IP | 외부 접속용 가상 LoadBalancer IP |
| Ingress | 도메인 기반 라우팅 (가상 호스트) |
| Windows hosts | 개발·테스트용 이름 해석 |
| 사내 DNS | 운영용 이름 해석 |

---

## 26. 실전 예시: VMware NAT 환경에서 Kubernetes 외부 접속

### 현재 VMware 네트워크 예시

```
VMnet1 (Host-only) : 192.168.111.1/24
VMnet8 (NAT)       : 192.168.253.1/24
```

VM이 NAT(VMnet8)에 연결된 경우, 게스트 VM 안에서 아래와 같은 주소를 받습니다.

```
게스트 VM IP       : 192.168.253.128  (DHCP 자동 할당)
```

### Kubernetes 내부 주소 구조

```
Pod IP         = 10.244.x.x     ← 클러스터 내부 전용
Service IP     = 10.96.x.x      ← 클러스터 내부 전용
MetalLB IP     = 192.168.253.200 ← 외부(Windows)에서 접근 가능
```

### Windows hosts 파일 설정 예시

파일 경로: `C:\Windows\System32\drivers\etc\hosts`

```
# Kubernetes 서비스 도메인 (MetalLB Ingress IP)
192.168.253.200  web.test.com
192.168.253.200  jup.test.com
192.168.253.200  harbor.test.com
192.168.253.200  nexus.test.com
```

> **참고**: hosts 파일 편집은 메모장을 **관리자 권한으로 실행** 한 뒤 위 경로를 열어야 합니다.

### 결론

브라우저에서 사용자가 실제로 접속하는 주소는 Pod IP나 ClusterIP가 아니라,
**MetalLB IP에 연결된 Ingress 도메인**입니다.

---

## 27. Ubuntu VM 단일 노드 Kubernetes 자동 설치

### 설치 스크립트 개요

이 저장소에는 VMware VM(Ubuntu 22.04/24.04) 위에 단일 노드 Kubernetes 클러스터를
자동으로 구성하는 셸 스크립트 `k8s-single-node-setup.sh` 가 포함되어 있습니다.

**설치 구성 요소**

| 구성 요소 | 버전/비고 |
|-----------|-----------|
| containerd | 최신 안정 버전 (Docker apt repo) |
| kubeadm / kubelet / kubectl | Kubernetes 1.29 |
| **Calico CNI** | v3.28.0 (Flannel 대체, Tigera Operator 방식) |
| **Metrics Server** | 최신 안정 버전 (단일 노드 insecure-tls 패치 포함) |
| **Headlamp** | v0.24.1 (CNCF 인큐베이팅, Helm Chart, LoadBalancer 노출) |
| MetalLB | v0.14.5 |
| NGINX Ingress Controller | v1.10.1 |

### Calico vs Flannel 비교

| 항목 | Flannel | Calico |
|------|---------|--------|
| 설치 복잡도 | 단순 (단일 YAML) | Tigera Operator 방식 |
| 네트워크 정책 | <i class="fa-solid fa-circle-xmark"></i> 미지원 | <i class="fa-solid fa-circle-check"></i> NetworkPolicy 완전 지원 |
| 캡슐화 | VXLAN | VXLAN / BGP / IPinIP 선택 가능 |
| 성능 | 보통 | 높음 (BGP 모드 시 오버헤드 없음) |
| 멀티 클러스터 | 제한적 | <i class="fa-solid fa-circle-check"></i> BGP 피어링 지원 |
| 운영 환경 채택 | 개발/학습 | 프로덕션 표준 |

> **이 스크립트에서는 VXLANCrossSubnet 캡슐화를 사용합니다.**  
> (동일 서브넷 내 Pod 간 통신은 오버헤드 없이 직접 라우팅, 서브넷 간에는 VXLAN 사용)

### Headlamp 대시보드 소개

Headlamp는 CNCF Incubating 프로젝트로, 기존 Kubernetes Dashboard의 단점을 개선한
최신 웹 기반 관리 UI 입니다.

| 항목 | 설명 |
|------|------|
| 설치 방식 | Helm Chart (LoadBalancer 타입으로 노출) |
| 인증 | Service Account 토큰 기반 |
| 기능 | 리소스 조회·수정, 로그 확인, Shell 접속, 플러그인 시스템 |
| 접속 URL | `http://<MetalLB-IP>` (MetalLB IP 풀에서 자동 할당) |

**접속 토큰 생성:**

```bash
# 관리자 ServiceAccount 생성
kubectl create serviceaccount headlamp-admin -n headlamp
kubectl create clusterrolebinding headlamp-admin \
  --clusterrole=cluster-admin \
  --serviceaccount=headlamp:headlamp-admin

# 토큰 발급 (브라우저 로그인 시 사용)
kubectl create token headlamp-admin -n headlamp
```

### Metrics Server 소개

Metrics Server는 `kubectl top` 명령어와 HPA(Horizontal Pod Autoscaler) 동작에 필요한
CPU / 메모리 사용량 데이터를 kubelet 에서 수집합니다.

```bash
# 노드 리소스 사용량 확인
kubectl top nodes

# Pod 리소스 사용량 확인
kubectl top pods -A
```

> **단일 노드 주의사항**: 자체 서명 인증서 환경에서 kubelet 메트릭을 수집하기 위해  
> `--kubelet-insecure-tls` 플래그가 자동으로 패치됩니다.

### 설치 단계 상세

```
 1/10  시스템 기본 설정  (swap 비활성화, 커널 모듈, sysctl)
 2/10  containerd 설치  (Docker apt repo, SystemdCgroup=true)
 3/10  kubeadm / kubelet / kubectl 설치 (pkgs.k8s.io, 버전 고정)
 4/10  kubeadm init  (단일 노드 클러스터 초기화, control-plane taint 제거)
 5/10  Calico CNI 설치  (Tigera Operator + Installation CR)
 6/10  Metrics Server 설치  (kubelet-insecure-tls 패치)
 7/10  Headlamp 대시보드 설치  (Helm, LoadBalancer 타입)
 8/10  MetalLB 설치 및 IPAddressPool 구성
 9/10  NGINX Ingress Controller 설치
10/10  설치 결과 출력
```

### 사전 요구 사항

| 항목 | 최소 사양 |
|------|----------|
| OS | Ubuntu 22.04 LTS 또는 24.04 LTS |
| CPU | 2코어 이상 |
| RAM | 4 GB 이상 (8 GB 권장) |
| Disk | 30 GB 이상 |
| 네트워크 | 인터넷 접속 가능 (패키지 다운로드) |
| 권한 | sudo 권한 필요 |

### 설치 방법

#### 1단계: 스크립트 다운로드 (또는 저장소 클론)

```bash
git clone https://github.com/edumgt/Dev-Lab-Install.git
cd Dev-Lab-Install
```

#### 2단계: MetalLB IP 범위 확인 및 수정 (선택)

VM 이 사용하는 네트워크 대역에 맞게 스크립트 상단의 변수를 수정합니다.

```bash
# k8s-single-node-setup.sh 상단 변수 (기본값 예시)
METALLB_IP_RANGE="192.168.253.200-192.168.253.220"
```

VM 의 실제 IP 대역 확인:

```bash
ip addr show        # VM 내부에서 실행
```

#### 3단계: 스크립트 실행

```bash
chmod +x k8s-single-node-setup.sh
sudo ./k8s-single-node-setup.sh
```

스크립트는 아래 10단계를 순서대로 자동 진행합니다.

#### 4단계: 설치 완료 확인

```bash
kubectl get nodes -o wide
kubectl get pods -A
kubectl get svc -n ingress-nginx
kubectl top nodes          # Metrics Server 동작 확인
```

정상 설치 시 출력 예시:

```
NAME       STATUS   ROLES           AGE   VERSION   INTERNAL-IP       ...
ubuntu-vm  Ready    control-plane   2m    v1.29.x   192.168.253.128   ...
```

### Windows hosts 파일 설정

설치 완료 후 스크립트가 출력하는 `Ingress LB IP` 값을 사용하여
Windows hosts 파일에 도메인을 등록합니다.

**hosts 파일 경로**: `C:\Windows\System32\drivers\etc\hosts`

```
# ── Kubernetes Ingress (MetalLB) ──────────────────────────
192.168.253.200  web.test.com
192.168.253.200  jup.test.com
192.168.253.200  harbor.test.com
192.168.253.200  nexus.test.com
192.168.253.200  gitlab.test.com
# ─────────────────────────────────────────────────────────
```

> **편집 방법**: 메모장(Notepad)을 **관리자 권한으로 실행** → 파일 열기 → 위 경로 입력 → 추가 후 저장

### 최종 요약

```
한 줄 요약
──────────────────────────────────────────────────────────────
VMware 환경에서 Kubernetes 서비스를 외부에서 쓰려면,
VM의 실제 네트워크 대역을 기준으로 MetalLB IP를 만들고,
그 IP에 Ingress 도메인을 연결하는 방식이 가장 깔끔합니다.
──────────────────────────────────────────────────────────────
```

---

## 28. VMware VM에 Nexus Repository Manager 설치

### 설치 목적
- Maven / npm / Docker / PyPI / Helm 패키지를 사내에서 캐싱·배포하는 범용 아티팩트 저장소
- 외부 인터넷 없이도 패키지를 프록시·호스팅하여 개발 환경 독립성 확보

### VM 사양 권장

| 항목 | 권장값 |
|------|-------|
| OS | Ubuntu 22.04 LTS |
| CPU | 4코어 이상 |
| RAM | 8 GB 이상 (JVM 기반) |
| Disk | 100 GB 이상 (저장소 데이터 포함) |
| 네트워크 | VMware NAT 또는 Bridged |

### 28-1) Java 17 설치 (Nexus 실행 필수)

```bash
sudo apt-get update -y
sudo apt-get install -y openjdk-17-jdk

# 버전 확인
java -version
```

### 28-2) Nexus 다운로드 및 설치

```bash
# 최신 버전 확인: https://help.sonatype.com/en/download.html
NEXUS_VERSION="3.68.0-04"
cd /opt

sudo wget -q "https://download.sonatype.com/nexus/3/nexus-${NEXUS_VERSION}-unix.tar.gz"
sudo tar -zxf "nexus-${NEXUS_VERSION}-unix.tar.gz"
sudo mv nexus-${NEXUS_VERSION} nexus
sudo rm -f "nexus-${NEXUS_VERSION}-unix.tar.gz"

# nexus 전용 사용자 생성
sudo useradd -r -d /opt/nexus -s /bin/false nexus
sudo chown -R nexus:nexus /opt/nexus /opt/sonatype-work
```

### 28-3) Nexus systemd 서비스 등록

```bash
sudo tee /etc/systemd/system/nexus.service > /dev/null <<'EOF'
[Unit]
Description=Sonatype Nexus Repository Manager
After=network.target

[Service]
Type=forking
User=nexus
ExecStart=/opt/nexus/bin/nexus start
ExecStop=/opt/nexus/bin/nexus stop
Restart=on-failure
LimitNOFILE=65536

[Install]
WantedBy=multi-user.target
EOF

sudo systemctl daemon-reload
sudo systemctl enable nexus
sudo systemctl start nexus
```

### 28-4) 초기 접속 및 설정

```bash
# 서비스 기동 대기 (약 1~2분 소요)
sudo journalctl -u nexus -f

# 초기 관리자 비밀번호 확인
sudo cat /opt/sonatype-work/nexus3/admin.password
```

브라우저에서 접속:
```
http://<VM-IP>:8081
```

| 항목 | 값 |
|------|-----|
| 기본 포트 | 8081 |
| 초기 계정 | admin |
| 초기 비밀번호 | `/opt/sonatype-work/nexus3/admin.password` 파일 내용 |

### 28-5) Maven 프록시 저장소 생성 예시

Nexus UI → **Administration** → **Repositories** → **Create repository**:

| 저장소 유형 | 이름 (예시) | Remote URL |
|------------|------------|------------|
| maven2 (proxy) | maven-central | `https://repo1.maven.org/maven2/` |
| npm (proxy) | npm-proxy | `https://registry.npmjs.org` |
| docker (hosted) | docker-hosted | — (내부 Push용) |
| helm (proxy) | helm-proxy | `https://charts.helm.sh/stable` |

### 28-6) Maven settings.xml 설정 예시

```xml
<!-- ~/.m2/settings.xml -->
<settings>
  <mirrors>
    <mirror>
      <id>nexus</id>
      <mirrorOf>*</mirrorOf>
      <url>http://<VM-IP>:8081/repository/maven-central/</url>
    </mirror>
  </mirrors>
  <servers>
    <server>
      <id>nexus</id>
      <username>admin</username>
      <password>your-password</password>
    </server>
  </servers>
</settings>
```

---

## 29. VMware VM에 Harbor Container Registry 설치

### 설치 목적
- Docker 이미지를 사내에 저장·관리하는 엔터프라이즈급 컨테이너 이미지 레지스트리
- 이미지 취약점 스캔(Trivy), RBAC, 복제(Replication) 기능 제공

### VM 사양 권장

| 항목 | 권장값 |
|------|-------|
| OS | Ubuntu 22.04 LTS |
| CPU | 2코어 이상 |
| RAM | 4 GB 이상 |
| Disk | 40 GB 이상 |
| 네트워크 | VMware NAT 또는 Bridged |

### 29-1) Docker 및 Docker Compose 설치

```bash
sudo apt-get update -y
sudo apt-get install -y ca-certificates curl gnupg

install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update -y
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin

# 현재 사용자를 docker 그룹에 추가
sudo usermod -aG docker $USER
newgrp docker

docker --version
docker compose version
```

### 29-2) Harbor 설치 파일 다운로드

```bash
# 최신 버전 확인: https://github.com/goharbor/harbor/releases
HARBOR_VERSION="v2.11.0"
cd /opt

sudo wget -q "https://github.com/goharbor/harbor/releases/download/${HARBOR_VERSION}/harbor-online-installer-${HARBOR_VERSION}.tgz"
sudo tar -zxf "harbor-online-installer-${HARBOR_VERSION}.tgz"
cd harbor
```

### 29-3) Harbor 설정 파일 수정

```bash
cp harbor.yml.tmpl harbor.yml
```

`harbor.yml` 주요 설정 항목:

```yaml
# harbor.yml

# VM 의 실제 IP 또는 도메인으로 변경
hostname: 192.168.253.100

# HTTP 포트 (HTTPS 사용 시 인증서 설정 필요)
http:
  port: 80

# HTTPS 비활성화 (테스트 환경 — 주석 처리)
# https:
#   port: 443
#   certificate: /your/certificate/path
#   private_key: /your/private/key/path

# 관리자 초기 비밀번호
harbor_admin_password: Harbor12345

# 데이터 저장 경로
data_volume: /data/harbor
```

### 29-4) Harbor 설치 및 시작

```bash
sudo mkdir -p /data/harbor
sudo ./install.sh --with-trivy   # 취약점 스캐너 Trivy 포함

# 서비스 상태 확인
docker compose ps
```

### 29-5) 초기 접속

브라우저에서 접속:
```
http://<VM-IP>
```

| 항목 | 값 |
|------|-----|
| 기본 포트 | 80 |
| 초기 계정 | admin |
| 초기 비밀번호 | Harbor12345 (harbor.yml 에서 변경 가능) |

### 29-6) Docker 클라이언트에서 Harbor 사용

```bash
# insecure-registries 설정 (HTTP 사용 시)
# /etc/docker/daemon.json
sudo tee /etc/docker/daemon.json > /dev/null <<'EOF'
{
  "insecure-registries": ["192.168.253.100"]
}
EOF
sudo systemctl restart docker

# Harbor 로그인
docker login 192.168.253.100
# Username: admin
# Password: Harbor12345

# 이미지 Push 예시
docker tag myapp:latest 192.168.253.100/library/myapp:latest
docker push 192.168.253.100/library/myapp:latest

# 이미지 Pull 예시
docker pull 192.168.253.100/library/myapp:latest
```

### 29-7) Kubernetes에서 Harbor 이미지 사용

```bash
# Harbor 인증 정보를 Kubernetes Secret으로 등록
kubectl create secret docker-registry harbor-secret \
  --docker-server=192.168.253.100 \
  --docker-username=admin \
  --docker-password=Harbor12345 \
  -n default
```

Deployment에 `imagePullSecrets` 추가:

```yaml
spec:
  template:
    spec:
      imagePullSecrets:
      - name: harbor-secret
      containers:
      - name: myapp
        image: 192.168.253.100/library/myapp:latest
```

---

## 30. VMware VM에 GitLab CE 설치

### 설치 목적
- 사내 Git 저장소, CI/CD 파이프라인(GitLab CI), 이슈 트래커를 한 곳에서 운영
- 코드 검토, 병합 요청(Merge Request), 컨테이너 레지스트리 내장

### VM 사양 권장

| 항목 | 권장값 |
|------|-------|
| OS | Ubuntu 22.04 LTS |
| CPU | 4코어 이상 |
| RAM | 8 GB 이상 (GitLab 최소 4 GB, 권장 8 GB) |
| Disk | 50 GB 이상 |
| 네트워크 | VMware NAT 또는 Bridged |

### 30-1) 의존 패키지 설치

```bash
sudo apt-get update -y
sudo apt-get install -y curl openssh-server ca-certificates tzdata perl postfix

# postfix 설치 시 "Internet Site" 선택, 시스템 메일 이름 입력
```

### 30-2) GitLab 패키지 저장소 등록 및 설치

```bash
# GitLab CE 공식 설치 스크립트
curl -fsSL https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh \
  | sudo bash

# external_url 을 VM 의 실제 IP 또는 도메인으로 지정하여 설치
sudo EXTERNAL_URL="http://192.168.253.101" apt-get install -y gitlab-ce
```

> 설치에 약 5~10분 소요됩니다.

### 30-3) GitLab 설정 적용

```bash
# 설정 변경 후 항상 실행
sudo gitlab-ctl reconfigure

# 서비스 상태 확인
sudo gitlab-ctl status
```

### 30-4) 초기 접속 및 비밀번호 확인

```bash
# 초기 root 비밀번호 확인 (설치 후 24시간 내 파일 자동 삭제됨)
sudo cat /etc/gitlab/initial_root_password
```

브라우저에서 접속:
```
http://192.168.253.101
```

| 항목 | 값 |
|------|-----|
| 기본 포트 | 80 (HTTP) |
| 초기 계정 | root |
| 초기 비밀번호 | `/etc/gitlab/initial_root_password` 파일 내용 |

### 30-5) 주요 gitlab.rb 설정

```bash
sudo vi /etc/gitlab/gitlab.rb
```

```ruby
# 외부 접속 URL
external_url 'http://192.168.253.101'

# 내장 NGINX 포트 변경 (다른 서비스와 충돌 시)
nginx['listen_port'] = 80

# 시간대 설정
gitlab_rails['time_zone'] = 'Asia/Seoul'

# 이메일 발신자 설정 (선택)
gitlab_rails['gitlab_email_from'] = 'gitlab@example.com'

# 레지스트리 포트 설정 (내장 컨테이너 레지스트리 사용 시)
registry_external_url 'http://192.168.253.101:5050'
```

설정 변경 후:
```bash
sudo gitlab-ctl reconfigure
sudo gitlab-ctl restart
```

### 30-6) GitLab Runner 설치 (CI/CD 실행 에이전트)

```bash
# GitLab Runner 패키지 저장소 등록
curl -fsSL https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh \
  | sudo bash

sudo apt-get install -y gitlab-runner

# Runner 등록 (GitLab UI 에서 토큰 확인: Settings → CI/CD → Runners)
sudo gitlab-runner register \
  --url "http://192.168.253.101" \
  --registration-token "<YOUR_TOKEN>" \
  --executor "shell" \
  --description "local-shell-runner" \
  --tag-list "shell,local"

# Runner 서비스 시작
sudo systemctl enable gitlab-runner
sudo systemctl start gitlab-runner
```

### 30-7) GitLab CI/CD 파이프라인 예시 (.gitlab-ci.yml)

```yaml
# .gitlab-ci.yml
stages:
  - build
  - test
  - deploy

variables:
  IMAGE: 192.168.253.100/library/myapp  # Harbor 레지스트리 경로

build:
  stage: build
  script:
    - docker build -t $IMAGE:$CI_COMMIT_SHA .
    - docker push $IMAGE:$CI_COMMIT_SHA

test:
  stage: test
  script:
    - docker run --rm $IMAGE:$CI_COMMIT_SHA ./run-tests.sh

deploy:
  stage: deploy
  script:
    - kubectl set image deployment/myapp myapp=$IMAGE:$CI_COMMIT_SHA
  only:
    - main
```

---

## 31. VMware VM에 NAS (OpenMediaVault) 설치

### 설치 목적
- 사내 파일 공유 서버(NFS / SMB / SFTP)를 VM 위에 구성
- 개발 환경에서 공유 볼륨, 백업 저장소, ISO 파일 서버로 활용
- OpenMediaVault(OMV)는 Debian 기반 NAS 전용 OS/소프트웨어

### VM 사양 권장

| 항목 | 권장값 |
|------|-------|
| OS | Debian 12 (Bookworm) 또는 Ubuntu 22.04 |
| CPU | 2코어 이상 |
| RAM | 2 GB 이상 |
| OS Disk | 20 GB (시스템용) |
| 데이터 Disk | 추가 가상 디스크 (50 GB 이상 권장) |
| 네트워크 | VMware NAT 또는 Bridged |

### 31-1) Debian 기반 VM에 OMV 설치 스크립트

```bash
# Debian 12 기준 설치 (root 권한 필요)
sudo apt-get update -y
sudo apt-get install -y gnupg curl

# OMV 공식 설치 스크립트 실행
curl -fsSL https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install \
  | sudo bash
```

> 설치에 약 10~20분 소요되며 완료 후 자동 재부팅됩니다.

### 31-2) Ubuntu 22.04 기반 VM에 OMV 6/7 설치

Ubuntu를 사용하는 경우에도 동일한 스크립트로 설치 가능합니다:

```bash
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y curl gnupg

# OMV 설치 스크립트 (Ubuntu/Debian 공용)
curl -fsSL https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install \
  | sudo bash

# 설치 중 네트워크 설정 변경 주의: SSH 접속이 끊길 수 있음
# 재부팅 후 VM 콘솔에서 IP 확인
```

### 31-3) 초기 접속

브라우저에서 접속 (기본 포트: 80):
```
http://<VM-IP>
```

| 항목 | 값 |
|------|-----|
| 기본 포트 | 80 |
| 초기 계정 | admin |
| 초기 비밀번호 | openmediavault |

> **최초 로그인 후 반드시 비밀번호를 변경하세요.**

### 31-4) 데이터 디스크 마운트 및 공유 설정

**① VMware에서 추가 가상 디스크 연결**
1. VM 설정 → **Add** → **Hard Disk** → 새 가상 디스크 추가 (예: 100 GB)
2. VM 재부팅 후 OMV 웹 UI에서 확인

**② OMV 웹 UI에서 파일 시스템 설정**
```
Storage → Disks        → 추가된 디스크 확인 (예: /dev/sdb)
Storage → File Systems → Create → 포맷 선택 (ext4 권장) → Mount
```

**③ 공유 폴더 생성**
```
Storage → Shared Folders → Add
  Name: shared-data
  File system: 위에서 마운트한 파일 시스템 선택
  Path: /shared-data
  Permissions: Everyone: read/write
```

### 31-5) SMB/CIFS 공유 설정 (Windows 파일 공유)

```
Services → SMB/CIFS → Settings → Enable: ON → Save → Apply

Services → SMB/CIFS → Shares → Add
  Shared folder: shared-data
  Name: shared-data
  Enable: ON
  Browseable: ON
  Read only: OFF
```

Windows 탐색기에서 접속:
```
\\<VM-IP>\shared-data
```

### 31-6) NFS 공유 설정 (Linux/Kubernetes 연동)

```
Services → NFS → Settings → Enable: ON → Save → Apply

Services → NFS → Shares → Add
  Shared folder: shared-data
  Client: 192.168.253.0/24   (접근 허용 네트워크 대역)
  Privilege: Read/Write
  Squash: No root squash
```

Linux 클라이언트에서 마운트:
```bash
sudo mount -t nfs 192.168.253.102:/shared-data /mnt/nas
```

### 31-7) Kubernetes PersistentVolume으로 NAS NFS 연동

```yaml
# nas-pv.yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: nas-nfs-pv
spec:
  capacity:
    storage: 50Gi
  accessModes:
    - ReadWriteMany
  nfs:
    server: 192.168.253.102    # NAS VM IP
    path: /shared-data
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: nas-nfs-pvc
spec:
  accessModes:
    - ReadWriteMany
  resources:
    requests:
      storage: 50Gi
  volumeName: nas-nfs-pv
```

```bash
kubectl apply -f nas-pv.yaml
kubectl get pv,pvc
```

---

## 32. VMware 개발 랩 전체 구성 요약

### 권장 VM 구성

| VM 역할 | OS | IP 예시 | 주요 서비스 | RAM |
|---------|-----|---------|------------|-----|
| k8s-node | Ubuntu 22.04 | 192.168.253.128 | Kubernetes (kubeadm) | 8 GB |
| nexus | Ubuntu 22.04 | 192.168.253.100 | Nexus Repository | 8 GB |
| harbor | Ubuntu 22.04 | 192.168.253.101 | Harbor Registry | 4 GB |
| gitlab | Ubuntu 22.04 | 192.168.253.102 | GitLab CE | 8 GB |
| nas | Debian 12 | 192.168.253.103 | OpenMediaVault NAS | 2 GB |

### 서비스 접속 포트 요약

| 서비스 | 접속 URL | 기본 계정 |
|-------|---------|----------|
| Kubernetes (Headlamp) | `http://192.168.253.200` | 토큰 기반 |
| Nexus | `http://192.168.253.100:8081` | admin / (초기 파일 확인) |
| Harbor | `http://192.168.253.101` | admin / Harbor12345 |
| GitLab | `http://192.168.253.102` | root / (초기 파일 확인) |
| NAS (OMV) | `http://192.168.253.103` | admin / openmediavault |

### Windows hosts 파일 전체 예시

`C:\Windows\System32\drivers\etc\hosts`:

```
# ── Kubernetes Ingress (MetalLB) ──────────────────────────
192.168.253.200  web.test.com
192.168.253.200  harbor.test.com
192.168.253.200  nexus.test.com
192.168.253.200  gitlab.test.com

# ── 직접 접속 서비스 ──────────────────────────────────────
192.168.253.100  nexus.lab
192.168.253.101  harbor.lab
192.168.253.102  gitlab.lab
192.168.253.103  nas.lab
# ──────────────────────────────────────────────────────────
```

### 전체 아키텍처 흐름

```
개발자 PC (Windows)
  │
  ├── VMware Workstation
  │     │
  │     ├── k8s-node   (192.168.253.128)
  │     │     ├── Kubernetes 클러스터
  │     │     │     ├── Calico CNI
  │     │     │     ├── Metrics Server
  │     │     │     ├── Headlamp Dashboard
  │     │     │     ├── MetalLB (192.168.253.200~220)
  │     │     │     └── NGINX Ingress
  │     │     └── 앱 Pod (spring-hello, node-hello, ...)
  │     │
  │     ├── nexus      (192.168.253.100:8081)  → Maven/npm/Docker 프록시
  │     ├── harbor     (192.168.253.101:80)    → 컨테이너 이미지 레지스트리
  │     ├── gitlab     (192.168.253.102:80)    → Git + CI/CD
  │     └── nas        (192.168.253.103:80)    → NFS/SMB 파일 공유
  │
  └── 브라우저 접속
        ├── http://nexus.lab:8081
        ├── http://harbor.lab
        ├── http://gitlab.lab
        ├── http://nas.lab
        └── http://192.168.253.200  (Headlamp)
```



---

## AI Agent 개발 환경 구성 가이드

> AI Agent(LLM 기반 코딩 보조 도구)를 개발 워크플로우에 통합하면 코드 작성, 리뷰, 테스트,
> 문서화 속도를 크게 높일 수 있습니다. 아래 각 섹션에서 도구별 API 키 발급·설치·사용 방법을
> 상세히 안내합니다.

---

### A1. Grok (xAI)

#### 개요
Elon Musk 가 설립한 xAI 에서 개발한 LLM. 실시간 X(Twitter) 데이터 접근 및 코드 생성에 강점.

#### API 키 발급
1. https://console.x.ai 접속 → 계정 생성 또는 로그인
2. **API Keys** → **Create API Key** 클릭
3. 생성된 키를 안전하게 복사

#### 환경 변수 설정
```bash
# Linux / macOS / WSL
echo 'export XAI_API_KEY="xai-your-key-here"' >> ~/.bashrc
source ~/.bashrc

# Windows PowerShell (영구 설정)
[System.Environment]::SetEnvironmentVariable("XAI_API_KEY", "xai-your-key-here", "User")
```

#### Python SDK 설치 및 사용

Grok API 는 OpenAI SDK 와 호환되는 인터페이스를 제공합니다.

```bash
pip install openai
```

```python
from openai import OpenAI

client = OpenAI(
    api_key=os.environ["XAI_API_KEY"],
    base_url="https://api.x.ai/v1",
)

response = client.chat.completions.create(
    model="grok-3",
    messages=[
        {"role": "system", "content": "You are a helpful coding assistant."},
        {"role": "user", "content": "Python 에서 REST API 를 호출하는 간단한 예시를 작성해줘."},
    ],
)
print(response.choices[0].message.content)
```

#### VS Code 연동
- 확장 마켓플레이스에서 **Continue** 확장 설치
- Continue 설정 파일(`~/.continue/config.json`)에 Grok 추가:

```json
{
  "models": [
    {
      "title": "Grok 3",
      "provider": "openai",
      "model": "grok-3",
      "apiBase": "https://api.x.ai/v1",
      "apiKey": "xai-your-key-here"
    }
  ]
}
```

---

### A2. Claude (Anthropic)

#### 개요
Anthropic 이 개발한 LLM. 안전성과 긴 컨텍스트(200K 토큰)에 강점. 코드 분석·리팩터링에 우수.

#### API 키 발급
1. https://console.anthropic.com 접속 → 계정 생성
2. **API Keys** → **Create Key** 클릭
3. 생성된 `sk-ant-...` 키 복사

#### 환경 변수 설정
```bash
echo 'export ANTHROPIC_API_KEY="sk-ant-your-key-here"' >> ~/.bashrc
source ~/.bashrc
```

#### Python SDK 설치 및 사용

```bash
pip install anthropic
```

```python
import anthropic
import os

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

message = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=1024,
    messages=[
        {
            "role": "user",
            "content": "아래 Python 코드를 리뷰하고 개선점을 알려줘:\n\ndef add(a,b):\n    return a+b",
        }
    ],
)
print(message.content[0].text)
```

#### Claude CLI (claude-code)

```bash
# Node.js 필요 (npm 환경)
npm install -g @anthropic-ai/claude-code

# 프로젝트 디렉터리에서 실행
cd my-project
claude

# 특정 작업 수행 (비대화형)
claude -p "이 프로젝트의 README 를 작성해줘"
```

#### MCP (Model Context Protocol) 서버 연동

Claude 는 MCP 를 통해 로컬 파일 시스템, DB, 외부 API 를 컨텍스트로 활용할 수 있습니다.

```bash
pip install mcp
```

`mcp_config.json` 예시:
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/home/user/projects"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token" }
    }
  }
}
```

#### VS Code 연동 — 공식 Claude Code 확장 (권장)

Anthropic이 공식 배포하는 **Claude Code** VS Code 확장은 별도 CLI 설치 없이도 에디터 안에서 바로 에이전트를 실행할 수 있습니다(내부적으로 `@anthropic-ai/claude-code` 엔진을 사용).

**설치 방법 (택 1)**
```bash
# 방법 1 — VS Code Marketplace에서 검색 후 설치
# 확장 검색창에 "Claude Code" 입력 → Anthropic 게시 확장 설치

# 방법 2 — CLI로 확장 ID 직접 설치
code --install-extension anthropic.claude-code

# 방법 3 — claude-code CLI가 이미 설치돼 있다면 터미널에서 자동 연동
npm install -g @anthropic-ai/claude-code
cd my-project
claude
# 대화 중 /ide 명령을 입력하면 열려 있는 VS Code 창에 자동으로 연결됨
```

**로그인 및 초기 설정**
1. VS Code 좌측 활동 표시줄(Activity Bar)에 추가된 **Claude** 아이콘 클릭
2. **Sign in with Claude.ai**(Pro/Max 구독) 또는 **Use Console API Key**(종량제, `sk-ant-...`) 중 선택
   - Claude.ai 계정 로그인 시 브라우저 창이 열리며 OAuth 인증 후 VS Code로 복귀
3. 우측 패널에 대화창이 표시되며, 코드 선택 후 **Add to Chat**으로 특정 파일/블록을 컨텍스트에 추가 가능
4. 파일 수정 제안은 diff 뷰로 표시되며 **Accept / Reject**로 승인 단위 제어

**주요 사용법**
```bash
# VS Code 통합 터미널에서 그대로 CLI 사용도 가능
claude "이 컴포넌트에 유닛 테스트를 추가해줘"

# 프로젝트 루트에 CLAUDE.md 생성 시 Claude Code가 자동으로 읽어 컨텍스트로 활용
```

`.vscode/settings.json` 에서 권한/자동승인 범위를 조정할 수 있습니다:
```json
{
  "claudeCode.permissions.allow": ["Bash(git diff:*)", "Bash(npm test:*)"],
  "claudeCode.autoInstallExtension": true
}
```

**대안 — Continue 확장으로 Claude API 직접 연동**
공식 확장 대신 범용 AI 코딩 확장인 **Continue**로 Claude API를 붙여 쓰고 싶을 때:

```json
{
  "models": [
    {
      "title": "Claude Opus 4.5",
      "provider": "anthropic",
      "model": "claude-opus-4-5",
      "apiKey": "sk-ant-your-key-here"
    }
  ]
}
```

---

### A3. ChatGPT / OpenAI API

#### 개요
OpenAI 가 개발한 GPT 시리즈. 범용 언어 이해·생성, 코드 생성, 이미지 분석(GPT-4o) 지원.

#### API 키 발급
1. https://platform.openai.com 접속 → 계정 생성
2. **API Keys** → **Create new secret key** 클릭
3. 생성된 `sk-...` 키 복사 (한 번만 표시되므로 즉시 저장)
4. **Billing** 에서 사용량 한도(Usage limit) 설정 권장

#### 환경 변수 설정
```bash
echo 'export OPENAI_API_KEY="sk-your-key-here"' >> ~/.bashrc
source ~/.bashrc
```

#### Python SDK 설치 및 사용

```bash
pip install openai
```

```python
from openai import OpenAI
import os

client = OpenAI(api_key=os.environ["OPENAI_API_KEY"])

# 텍스트 생성
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a senior Python developer."},
        {"role": "user", "content": "FastAPI 로 CRUD API 를 작성하는 기본 구조를 알려줘."},
    ],
    temperature=0.2,
)
print(response.choices[0].message.content)

# 스트리밍 출력
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "파이썬 제너레이터를 설명해줘."}],
    stream=True,
)
for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

#### 비용 관리 팁
| 모델 | 용도 | 비용 수준 |
|------|------|----------|
| gpt-4o-mini | 일반 코드 보조, 간단한 질의 | 낮음 |
| gpt-4o | 복잡한 코드 분석·생성 | 중간 |
| o3 / o4-mini | 수학·알고리즘·추론 | 높음 |

```bash
# 사용량 모니터링 (Usage API)
curl https://api.openai.com/v1/usage \
  -H "Authorization: Bearer $OPENAI_API_KEY"
```

---

### A4. OpenAI Codex CLI

#### 개요
OpenAI Codex CLI 는 터미널에서 자연어로 코드 작업을 수행하는 AI 코딩 에이전트.
파일 읽기·수정, 명령 실행, 테스트 실행을 자율적으로 처리.

#### 설치

```bash
# Node.js 18+ 필요
npm install -g @openai/codex

# 버전 확인
codex --version
```

#### API 키 설정

```bash
export OPENAI_API_KEY="sk-your-key-here"
```

#### 기본 사용법

```bash
# 대화형 실행 (기본 sandbox 모드 — 파일 수정·명령 실행 전 승인 요청)
codex

# 특정 작업 실행
codex "이 프로젝트에 pytest 테스트를 추가해줘"

# 전체 자동 승인 모드 (주의: 파일이 자동 수정됨)
codex --approval-mode full-auto "requirements.txt 기반으로 Docker 이미지를 최적화해줘"

# 특정 모델 사용
codex --model o4-mini "버그를 찾아서 수정해줘"
```

#### 승인 모드 옵션

| 모드 | 설명 |
|------|------|
| `suggest` (기본) | 모든 변경 전 확인 요청 |
| `auto-edit` | 파일 수정은 자동, 명령 실행은 확인 |
| `full-auto` | 모든 작업 자동 처리 (신중하게 사용) |

#### 프로젝트별 지시사항 (`AGENTS.md`)

프로젝트 루트에 `AGENTS.md` 파일을 생성하면 Codex 가 자동으로 읽습니다:

```markdown
# Project Guidelines for AI Agents

## 코드 스타일
- Python: black 포매터, ruff 린터 사용
- 타입 힌트 필수 (mypy strict 모드)

## 테스트
- 모든 함수에 pytest 테스트 작성
- `pytest --cov=src` 로 커버리지 확인

## 금지 사항
- 프로덕션 DB에 직접 연결하지 말 것
- `.env` 파일 절대 수정 금지
```

#### VS Code 연동 — 공식 Codex 확장

OpenAI가 공식 배포하는 **Codex** VS Code 확장을 사용하면 CLI 없이도 에디터 내에서 동일한 에이전트를 사용할 수 있습니다.

**설치 방법 (택 1)**
```bash
# 방법 1 — VS Code Marketplace에서 검색 후 설치
# 확장 검색창에 "Codex" 입력 → OpenAI 게시 확장(openai.chatgpt) 설치

# 방법 2 — CLI로 확장 ID 직접 설치
code --install-extension openai.chatgpt

# 방법 3 — codex CLI가 설치돼 있다면 터미널에서 확장 자동 설치 안내를 따라도 됨
npm install -g @openai/codex
```

**로그인 및 초기 설정**
1. VS Code 좌측 활동 표시줄에 추가된 **Codex** 아이콘 클릭
2. 인증 방식 선택
   - **Sign in with ChatGPT**(Plus/Pro/Team/Enterprise 구독 — 별도 API 과금 없이 구독 한도 내 사용)
   - **Use API key**(`sk-...`, 종량제 과금, `OPENAI_API_KEY` 환경변수 또는 확장 설정에 직접 입력)
3. 우측 패널의 대화창에서 작업 지시 → 파일 변경은 diff로 표시되고 승인 모드(Suggest/Auto-edit/Full-auto)는 CLI와 동일하게 설정에서 조정
4. 워크스페이스에 `AGENTS.md`가 있으면 확장도 CLI와 동일하게 자동으로 읽어 컨텍스트로 사용

`.vscode/settings.json` 예시:
```json
{
  "openai.chatgpt.approvalMode": "auto-edit",
  "openai.chatgpt.model": "o4-mini"
}
```

> Codex CLI와 VS Code 확장은 동일한 인증 세션(`codex login`으로 로그인한 ChatGPT 계정 또는 API 키)을 공유하므로, 터미널에서 로그인해 두면 확장에서 다시 로그인할 필요가 없는 경우가 많습니다.

---

### A5. GitHub Copilot

#### 개요
GitHub + OpenAI 가 공동 개발한 AI 코딩 보조 도구. VS Code, JetBrains IDE, Neovim, CLI 지원.
개인/팀/기업 플랜 제공 (학생·오픈소스 기여자 무료).

#### 구독 설정
1. https://github.com/settings/copilot 접속
2. **Enable GitHub Copilot** 클릭 (무료 체험 또는 구독)
3. 결제 정보 입력 (Individual: $10/월, Business: $19/월·사용자)

#### VS Code 확장 설치

```bash
# VS Code 명령 팔레트 (Ctrl+Shift+P)
# "Extensions: Install Extensions" → "GitHub Copilot" 검색 및 설치
# 또는 CLI 로 설치
code --install-extension GitHub.copilot
code --install-extension GitHub.copilot-chat
```

**로그인 방법**:
- VS Code 하단 상태바 Copilot 아이콘 클릭 → **Sign In to GitHub** → 브라우저에서 인증

#### VS Code 에서 Copilot 기능 활용

| 기능 | 단축키 / 사용법 |
|------|----------------|
| 코드 자동 완성 | 코드 작성 중 자동 표시 → `Tab` 수락 |
| 인라인 코드 생성 | `Ctrl+I` → 자연어로 코드 요청 |
| Copilot Chat | `Ctrl+Alt+I` 또는 사이드바 Chat 패널 |
| 코드 설명 | 코드 선택 후 우클릭 → **Copilot: Explain This** |
| 코드 수정 | 코드 선택 후 `Ctrl+I` → "/fix 오류 수정해줘" |
| 테스트 생성 | 함수 선택 후 Chat에서 `/tests` 입력 |
| 문서화 | 함수 선택 후 `/doc` 입력 |

#### Copilot Chat 슬래시 명령어

```
/explain  — 선택 코드 설명
/fix      — 버그 수정 제안
/tests    — 테스트 코드 생성
/doc      — 문서(docstring) 생성
/simplify — 코드 단순화
/new      — 새 파일/프로젝트 스캐폴딩
@workspace — 전체 프로젝트 컨텍스트 참조
@terminal  — 터미널 명령어 도움
```

#### GitHub Copilot CLI

```bash
# 설치
npm install -g @githubnext/github-copilot-cli

# GitHub 계정 인증
github-copilot-cli auth

# 사용법
github-copilot-cli what-the-shell "현재 디렉터리의 Python 파일을 모두 찾아줘"
github-copilot-cli git-assist "최근 3개 커밋을 하나로 합쳐줘"
github-copilot-cli explain "docker run -it --rm -v $(pwd):/app python:3.12"
```

#### `.github/copilot-instructions.md` — 리포지터리별 Copilot 지시사항

프로젝트 내 `.github/copilot-instructions.md` 파일을 생성하면 Copilot 이 자동으로 컨텍스트로 활용합니다:

```markdown
# Copilot Instructions

이 프로젝트는 FastAPI 기반 REST API 서버입니다.

## 코딩 규칙
- Python 3.12+ 문법 사용
- 모든 함수에 타입 힌트 및 docstring 작성
- 비동기(async/await) 패턴 우선 사용
- 예외 처리는 커스텀 예외 클래스 사용

## 테스트
- pytest + httpx 로 API 테스트 작성
- 모든 엔드포인트에 최소 1개 이상 테스트 필수
```

#### GitHub Copilot Agent (Coding Agent)

GitHub 이 제공하는 자율 코딩 에이전트. GitHub 이슈를 할당하면 자동으로 코드를 작성하고 PR 을 생성합니다.

**사용 방법**:
1. GitHub 이슈 생성 (상세한 요구사항 작성)
2. Assignee 를 **Copilot** 으로 설정
3. 에이전트가 브랜치 생성 → 코드 구현 → PR 생성
4. PR 에서 결과 검토 및 리뷰 코멘트 추가
5. 에이전트가 피드백을 반영하여 추가 수정

**효과적인 이슈 작성 팁**:
```markdown
## 작업 내용
사용자 인증 엔드포인트(`POST /auth/login`)를 구현해주세요.

## 요구사항
- 이메일 + 패스워드로 로그인
- JWT 토큰 반환 (access + refresh)
- 잘못된 인증 정보 시 401 응답
- bcrypt 로 비밀번호 해시 처리

## 기술 스택
- FastAPI, SQLAlchemy, python-jose, passlib

## 테스트
- pytest 로 정상·실패 케이스 모두 커버
```

---

### A6. Google Gemini

#### 개요
Google DeepMind 가 개발한 멀티모달 LLM. 코드 생성, 이미지·문서 분석, 긴 컨텍스트(1M 토큰) 지원.
Gemini API 는 무료 티어 제공.

#### API 키 발급
1. https://aistudio.google.com 접속 → Google 계정 로그인
2. **Get API Key** → **Create API key** 클릭
3. 생성된 `AIza...` 키 복사

#### 환경 변수 설정
```bash
echo 'export GEMINI_API_KEY="AIza-your-key-here"' >> ~/.bashrc
source ~/.bashrc
```

#### Python SDK 설치 및 사용

```bash
pip install google-genai
```

```python
from google import genai
import os

client = genai.Client(api_key=os.environ["GEMINI_API_KEY"])

# 텍스트 생성
response = client.models.generate_content(
    model="gemini-2.5-pro",
    contents="Python 에서 데코레이터 패턴을 설명하고 실용적인 예시를 작성해줘.",
)
print(response.text)

# 코드 실행 도구 활성화
response = client.models.generate_content(
    model="gemini-2.5-pro",
    contents="피보나치 수열 100번째 항을 계산해줘.",
    config={"tools": [{"code_execution": {}}]},
)
print(response.text)
```

#### Gemini CLI

```bash
# Node.js 필요
npm install -g @google/gemini-cli

# 인증 (Google 계정 또는 API 키)
gemini auth login

# API 키 방식
export GEMINI_API_KEY="AIza-your-key-here"

# 대화형 실행
gemini

# 비대화형 명령
gemini -p "이 Python 파일을 분석하고 리팩터링 제안을 해줘" < main.py

# 특정 모델 사용
gemini --model gemini-2.5-pro "이 코드의 시간복잡도를 분석해줘"
```

#### VS Code 연동 (Google Cloud Code 확장)

```bash
code --install-extension GoogleCloudTools.cloudcode
```

또는 **Continue** 확장으로 Gemini 연동:

```json
{
  "models": [
    {
      "title": "Gemini 2.5 Pro",
      "provider": "gemini",
      "model": "gemini-2.5-pro",
      "apiKey": "AIza-your-key-here"
    }
  ]
}
```

#### Gemini 무료 티어 한도 (2025년 기준)
| 모델 | 무료 요청 한도 |
|------|--------------|
| Gemini 2.0 Flash | 1,500 req/day |
| Gemini 2.5 Pro | 25 req/day |
| Gemini 1.5 Flash | 1,500 req/day |

---

### A6-1. Ollama (로컬 LLM)

#### 개요
Ollama는 로컬 PC에서 open-weight LLM을 직접 내려받아 실행할 수 있는 도구입니다.
API 비용 없이 오프라인/사내망 환경에서도 사용할 수 있어 개인 학습, 보안 제약 환경, 빠른 프로토타이핑에 적합합니다.

#### 설치 전 권장 사양
| 모델 크기 예시 | 권장 RAM | 비고 |
|---------------|----------|------|
| 3B ~ 7B | 16GB 이상 | 입문/학습용 |
| 8B ~ 14B | 32GB 이상 | 코드 생성/리뷰 품질 향상 |
| 32B 이상 | 64GB 이상 | 고사양 워크스테이션 권장 |

#### 설치 방법

**Windows**
```powershell
winget install Ollama.Ollama
```

또는 공식 사이트에서 설치:
- https://ollama.com/download/windows

**macOS**
```bash
brew install --cask ollama
```

또는 공식 사이트에서 설치:
- https://ollama.com/download/mac

**Linux / WSL**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

설치 확인:
```bash
ollama --version
```

#### 첫 실행 및 모델 다운로드

```bash
# 서버 실행 (macOS/Linux/WSL)
ollama serve
```

Windows는 설치 후 Ollama 앱이 백그라운드에서 실행되는지 확인하면 됩니다.

```bash
# 범용 모델 예시
ollama pull llama3.1:8b

# 코딩 특화 모델 예시
ollama pull qwen2.5-coder:7b
```

#### 기본 사용법

```bash
# 대화형 실행
ollama run qwen2.5-coder:7b

# 설치된 모델 목록
ollama list

# 현재 실행 중인 모델 확인
ollama ps

# 모델 삭제
ollama rm qwen2.5-coder:7b
```

#### 로컬 API 호출 예시

Ollama는 기본적으로 `http://localhost:11434`에 OpenAI 호환 형태의 로컬 API를 제공합니다.

```bash
curl http://localhost:11434/api/generate \
  -d '{
    "model": "qwen2.5-coder:7b",
    "prompt": "FastAPI hello world 예제를 작성해줘",
    "stream": false
  }'
```

#### VS Code / Continue 연동 예시

```json
{
  "models": [
    {
      "title": "Qwen2.5 Coder 7B (Ollama)",
      "provider": "ollama",
      "model": "qwen2.5-coder:7b"
    }
  ]
}
```

#### 운영 팁
- 처음 모델을 받을 때는 수 GB 이상 다운로드가 발생할 수 있으므로 디스크 여유 공간을 먼저 확인하세요.
- 노트북에서는 배터리/발열 영향이 크므로 전원 연결 상태에서 실행하는 것을 권장합니다.
- 사내망/오프라인 환경에서는 먼저 설치 파일과 모델 다운로드 가능 여부를 확인하세요.

### 공식 사이트
- https://ollama.com/
- https://ollama.com/search

---

### A7. AI Agent 도구 비교 및 선택 가이드

| 도구 | 제공사 | 무료 여부 | 주요 강점 | 코딩 특화 기능 |
|------|--------|----------|-----------|---------------|
| Grok | xAI | API 유료 | 실시간 데이터, 긴 컨텍스트 | 코드 생성·디버깅 |
| Claude | Anthropic | API 유료 (무료 웹 UI) | 안전성, 200K 컨텍스트, 코드 리뷰 | claude-code CLI, MCP |
| ChatGPT | OpenAI | 웹 무료, API 유료 | 범용 이해, GPT-4o 멀티모달 | Function Calling, 플러그인 |
| Codex CLI | OpenAI | API 비용 발생 | 터미널 자율 에이전트 | 파일 수정·명령 실행 자동화 |
| Copilot | GitHub/MS | 개인 $10/월 (학생 무료) | IDE 깊은 통합, PR 에이전트 | 자동완성, Chat, Coding Agent |
| Gemini | Google | 무료 티어 제공 | 1M 컨텍스트, 멀티모달 | 코드 실행 도구 내장 |
| Ollama | Ollama | 로컬 실행 무료 | 로컬 모델, 오프라인 사용, 비용 예측 쉬움 | 로컬 추론, 자체 API, Continue 연동 |

#### 시나리오별 권장 조합

**개인 학습 / 사이드 프로젝트**
- Gemini (무료 티어) + Ollama (로컬 모델) + GitHub Copilot (무료 플랜) + Continue 확장

**팀 개발 / 스타트업**
- GitHub Copilot Business + Claude API (코드 리뷰 자동화) + Codex CLI

**엔터프라이즈 / 사내망**
- GitHub Copilot Enterprise + Ollama (사내 로컬 모델) + MCP 서버

---

### A8. 개인 AI 개발 환경 통합 설정

#### 공통 환경 변수 관리 (`.env` 파일 활용)

프로젝트 루트에 `.env` 파일 생성 (`.gitignore` 에 추가 필수):

```bash
# .env — 절대 Git 에 커밋하지 마세요!
OPENAI_API_KEY=sk-your-openai-key
ANTHROPIC_API_KEY=sk-ant-your-anthropic-key
GEMINI_API_KEY=AIza-your-gemini-key
XAI_API_KEY=xai-your-xai-key
GITHUB_TOKEN=ghp-your-github-token
OLLAMA_HOST=http://localhost:11434
```

```bash
# .gitignore 에 추가
echo ".env" >> .gitignore
echo ".env.local" >> .gitignore
```

**Python 에서 `.env` 로드**:

```bash
pip install python-dotenv
```

```python
from dotenv import load_dotenv
import os

load_dotenv()  # .env 파일 자동 로드

openai_key = os.getenv("OPENAI_API_KEY")
anthropic_key = os.getenv("ANTHROPIC_API_KEY")
ollama_host = os.getenv("OLLAMA_HOST", "http://localhost:11434")
```

#### Continue 확장으로 여러 AI 모델 통합 (`~/.continue/config.json`)

VS Code 에서 **Continue** 확장 하나로 모든 AI 모델을 전환하며 사용할 수 있습니다.

```bash
# Continue 확장 설치
code --install-extension Continue.continue
```

```json
{
  "models": [
    {
      "title": "GPT-4o",
      "provider": "openai",
      "model": "gpt-4o",
      "apiKey": "sk-your-openai-key"
    },
    {
      "title": "Claude Opus 4.5",
      "provider": "anthropic",
      "model": "claude-opus-4-5",
      "apiKey": "sk-ant-your-anthropic-key"
    },
    {
      "title": "Gemini 2.5 Pro",
      "provider": "gemini",
      "model": "gemini-2.5-pro",
      "apiKey": "AIza-your-gemini-key"
    },
    {
      "title": "Grok 3",
      "provider": "openai",
      "model": "grok-3",
      "apiBase": "https://api.x.ai/v1",
      "apiKey": "xai-your-xai-key"
    },
    {
      "title": "Qwen2.5 Coder 7B (Local)",
      "provider": "ollama",
      "model": "qwen2.5-coder:7b"
    }
  ],
  "tabAutocompleteModel": {
    "title": "Copilot (자동완성)",
    "provider": "github",
    "model": "copilot"
  },
  "contextProviders": [
    { "name": "code" },
    { "name": "docs" },
    { "name": "diff" },
    { "name": "terminal" },
    { "name": "problems" },
    { "name": "folder" },
    { "name": "codebase" }
  ],
  "slashCommands": [
    { "name": "edit", "description": "코드 수정" },
    { "name": "comment", "description": "주석 추가" },
    { "name": "tests", "description": "테스트 생성" },
    { "name": "share", "description": "대화 공유" }
  ]
}
```

#### AI 코딩 워크플로우 권장 순서

```
1. 기능 설계
   └─ ChatGPT / Claude → 아키텍처 설계, 기술 선택 논의

2. 코드 작성
   └─ GitHub Copilot → IDE 내 실시간 자동완성·인라인 생성

3. 코드 리뷰
   └─ Claude / Gemini → 코드 품질·보안·성능 검토

4. 자동화 작업 (반복적 구현)
   └─ Codex CLI / Copilot Agent → 파일 수정, 테스트 작성, 리팩터링 자동화

5. 배포·운영 질의
   └─ Grok / Gemini → 최신 기술 동향, 실시간 문서 검색
```

---

## <i class="fa-brands fa-aws"></i> 개발 워크플로우 관리 도구 — AWS CodeCatalyst · Jira · Azure DevOps

소프트웨어 개발 팀은 **소스 코드 관리 + 이슈 트래킹 + CI/CD 파이프라인**을 하나의 흐름으로 연결하는 워크플로우 플랫폼이 필요합니다. 대표적인 세 가지 도구를 상세히 비교합니다.

### 도구 비교 요약

| 항목 | AWS CodeCatalyst | Jira (Atlassian) | Azure DevOps |
|------|-----------------|-----------------|--------------|
| **운영 주체** | Amazon Web Services | Atlassian | Microsoft |
| **핵심 강점** | AWS 서비스 네이티브 통합 | 이슈 트래킹·애자일 관리 최강 | MS 생태계 통합, All-in-One |
| **무료 티어** | 3명·개인 프로젝트 무료 | 10명 이하 무료 | 5명 이하 무료 |
| **CI/CD** | CodePipeline·빌드 포함 | Bitbucket Pipelines (별도) | Azure Pipelines 내장 |
| **코드 저장소** | 내장 Git 저장소 | 없음 (GitHub·Bitbucket 연동) | Azure Repos 내장 |
| **칸반 보드** | 내장 이슈 + 백로그 | 고급 칸반·스프린트 보드 | Azure Boards 내장 |
| **적합 대상** | AWS 기반 개발팀 | 대규모 애자일 팀 | MS/Azure 기반 팀 |

---

### 1. AWS Code 시리즈 & CodeCatalyst

#### 1-1. AWS Code 시리즈 전체 구성

AWS는 CI/CD 파이프라인을 구성하는 개별 서비스와, 이를 통합하는 CodeCatalyst 두 가지 방향을 제공합니다.

```
┌─────────────────────────────────────────────────────────────────┐
│                    AWS Code 시리즈 생태계                        │
│                                                                  │
│  CodeCatalyst (통합 플랫폼) ──────────────────────────────┐     │
│                                                           │     │
│  ┌──────────────┐  ┌──────────────┐  ┌─────────────────┐ │     │
│  │ CodeCommit   │  │  CodeBuild   │  │  CodeDeploy     │ │     │
│  │ (Git 저장소) │→ │ (빌드/테스트)│→ │ (EC2·ECS·Lambda)│ │     │
│  └──────────────┘  └──────────────┘  └─────────────────┘ │     │
│           │               │                  │             │     │
│           └───────────────┴──────────────────┘             │     │
│                           ▼                                │     │
│                   CodePipeline (전체 파이프라인 오케스트레이션)   │
│                                                           │     │
│  CodeArtifact (패키지 저장소) · CodeGuru (AI 코드 리뷰)  ◄┘     │
└─────────────────────────────────────────────────────────────────┘
```

| 서비스 | 역할 | 핵심 용도 |
|--------|------|----------|
| **CodeCommit** | Git 기반 소스 저장소 | AWS IAM으로 접근 제어, 프라이빗 Git 호스팅 |
| **CodeBuild** | 완전관리형 빌드 서버 | Docker 빌드, 단위 테스트, 아티팩트 생성 |
| **CodeDeploy** | 배포 자동화 | EC2, ECS, Lambda, On-Premise 무중단 배포 |
| **CodePipeline** | CI/CD 오케스트레이션 | 소스→빌드→테스트→배포 파이프라인 시각화 |
| **CodeArtifact** | 패키지 저장소 | npm, Maven, PyPI 프라이빗 패키지 관리 |
| **CodeGuru** | AI 코드 리뷰 | 자동 코드 품질·보안 취약점 분석 (Reviewer), 성능 병목 탐지 (Profiler) |
| **CodeCatalyst** | 통합 개발 플랫폼 | 위 서비스 + 이슈 트래킹 + 팀 협업 통합 |

#### 1-2. AWS CodeCatalyst 상세 가이드

**CodeCatalyst**는 2023년 GA(일반 출시)된 AWS의 통합 소프트웨어 개발 플랫폼입니다. 소스 코드, CI/CD 파이프라인, 이슈 트래킹, 팀 관리를 단일 인터페이스에서 제공합니다.

##### 핵심 개념

```
Space (조직 단위)
  └── Project (프로젝트)
        ├── Source Repository (Git 저장소 — 내장 또는 GitHub 연동)
        ├── Workflows (CI/CD 파이프라인)
        ├── Issues (이슈 트래킹 + 백로그)
        ├── Dev Environment (클라우드 IDE — VS Code/JetBrains 원격 연결)
        └── Reports (테스트·코드 커버리지 리포트)
```

##### 가입 및 초기 설정

**Step 1 — AWS Builder ID 생성 (CodeCatalyst 전용 계정)**

```
1. https://codecatalyst.aws 접속
2. [Get started for free] 클릭
3. [Create AWS Builder ID] 선택
   - 이메일 주소 입력
   - 인증 이메일 수신 후 코드 입력
   - 이름(표시 이름) 설정
   ※ AWS Builder ID는 기존 AWS 계정과 별개 — 별도 가입 필요
4. [Create a Space] 클릭
   - Space 이름 입력 (조직·팀 이름)
   - AWS 계정 연결 (AWS 리소스 배포 시 필요 — 선택)
   - 리전 선택 (ap-northeast-2 = 서울)
```

**Step 2 — 프로젝트 생성**

```
1. Space 대시보드 → [Create project]
2. 방식 선택:
   Option A: [Start with a blueprint]
     → 미리 구성된 템플릿 선택 (웹앱, 서버리스, 컨테이너 등)
   Option B: [Start from scratch]
     → 빈 프로젝트 → 직접 구성
3. 프로젝트 이름 입력 → [Create project]
```

**Step 3 — 소스 저장소 연결**

```bash
# 방법 A: CodeCatalyst 내장 Git 저장소 사용
# 프로젝트 → Source repositories → [Add repository] → [Create repository]
# → 저장소 이름 입력 → [Create]

# 로컬 클론
git clone https://git.us-west-2.codecatalyst.aws/v1/MySpace/MyProject/MyRepo
# AWS Builder ID로 인증 (PAT — Personal Access Token 발급 필요)

# 방법 B: GitHub 저장소 연동
# Source repositories → [Add repository] → [Link GitHub repository]
# → GitHub App 설치 → 저장소 선택
```

**Step 4 — PAT(Personal Access Token) 발급**

```
1. 우측 상단 프로필 아이콘 → [My settings]
2. [Personal access tokens] → [Generate personal access token]
3. 토큰 이름 입력, 만료일 설정
4. [Generate token] → 토큰 복사 (재표시 불가)

# Git 자격증명으로 사용
git config --global credential.helper store
# 이후 clone/push 시 사용자명: AWS Builder ID 이메일, 비밀번호: 발급한 PAT
```

##### Workflow (CI/CD 파이프라인) 구성

CodeCatalyst Workflow는 YAML로 정의하며 `.codecatalyst/workflows/` 에 저장됩니다.

```yaml
# .codecatalyst/workflows/main-pipeline.yaml
Name: main-pipeline
SchemaVersion: "1.0"

Triggers:
  - Type: Push
    Branches:
      - main

Actions:
  Build:
    Identifier: aws/build@v1
    Inputs:
      Sources:
        - WorkflowSource
    Configuration:
      Steps:
        - Run: pip install -r requirements.txt
        - Run: pytest tests/ --junitxml=test-results.xml
    Outputs:
      Reports:
        TestReport:
          Format: JUNITXML
          IncludePaths:
            - test-results.xml

  Deploy:
    Identifier: aws/ecs-deploy@v1
    DependsOn:
      - Build
    Environment:
      Name: Production
      Connections:
        - AccountId: "123456789012"
          Role: CodeCatalystDeployRole
    Configuration:
      cluster: my-ecs-cluster
      service: my-ecs-service
      task-definition: task-def.json
      region: ap-northeast-2
```

```bash
# 워크플로우 파일 커밋 → 자동 트리거
git add .codecatalyst/workflows/main-pipeline.yaml
git commit -m "feat: add CI/CD pipeline"
git push origin main
# → CodeCatalyst 콘솔에서 실행 현황 실시간 확인 가능
```

##### Dev Environment (클라우드 IDE)

CodeCatalyst는 **클라우드 기반 개발 환경**을 제공합니다. 로컬 환경 설치 없이 VS Code 또는 JetBrains를 원격으로 연결해 개발할 수 있습니다.

```
1. 프로젝트 → [Dev Environments] → [Create Dev Environment]
2. IDE 선택: VS Code (권장) / JetBrains / Cloud9
3. 인스턴스 크기 선택:
   - Dev.Standard1.Small  (2 vCPU, 4 GB RAM)  — 경량 작업
   - Dev.Standard1.Medium (4 vCPU, 8 GB RAM)  — 일반 개발
   - Dev.Standard1.Large  (8 vCPU, 16 GB RAM) — 빌드·ML 작업
4. 저장소 브랜치 선택 → [Create]
5. VS Code 원격 연결 → 자동으로 소스 코드 클론 완료
```

##### 이슈(Issues) & 백로그 관리

```
이슈 생성:
  프로젝트 → Issues → [Create issue]
  - 제목, 설명, 담당자, 우선순위, 스프린트, 레이블 설정

이슈 상태 흐름:
  Backlog → In Progress → In Review → Done

이슈와 PR 연결:
  커밋 메시지에 이슈 번호 포함 → 자동 연결
  예) git commit -m "fix: 로그인 오류 수정 /issue/42"
```

##### 무료 티어 한도 (2024 기준)

| 리소스 | 무료 한도/월 |
|--------|------------|
| 사용자 수 | 3명 |
| 빌드 시간 | 2,000분 |
| 소스 저장소 용량 | 10 GB |
| Dev Environment | 60시간 |
| 아티팩트 저장소 | 5 GB |

> 초과 시 AWS 계정에 종량제 요금 부과 (계정 연결 필요)

##### AWS CodeCatalyst vs 개별 Code 서비스 선택 가이드

```
CodeCatalyst 선택 기준:
  ✅ 새 프로젝트를 처음부터 AWS에서 시작
  ✅ 소스·CI/CD·이슈 트래킹을 하나로 관리
  ✅ 클라우드 IDE로 팀원이 동일 환경에서 개발

개별 서비스 (CodePipeline + CodeBuild + CodeDeploy) 선택 기준:
  ✅ 기존 GitHub/GitLab 저장소 유지하면서 AWS 배포만 자동화
  ✅ 세밀한 IAM 권한 제어 필요
  ✅ 기존 CI/CD 시스템과 연동
```

---

### 2. Jira — 칸반 & 스크럼 프로젝트 관리

Jira는 Atlassian이 개발한 **이슈 트래킹 + 애자일 프로젝트 관리 플랫폼**입니다. 전 세계 소프트웨어 팀에서 가장 많이 사용되는 협업 도구 중 하나입니다.

#### 2-1. 핵심 개념

```
Organization (조직)
  └── Site (사이트 — example.atlassian.net)
        └── Project (프로젝트)
              ├── Board (칸반 또는 스크럼 보드)
              ├── Backlog (백로그 — 스크럼 전용)
              ├── Roadmap (로드맵)
              ├── Issues (이슈)
              └── Reports (번다운 차트, 속도 차트 등)
```

| 개념 | 설명 |
|------|------|
| **Epic** | 큰 기능 단위 (여러 Story/Task 포함, 수주~수개월) |
| **Story** | 사용자 관점의 기능 요구사항 ("사용자로서 나는 …할 수 있다") |
| **Task** | 개발 작업 단위 (Epic·Story보다 작음) |
| **Bug** | 결함 보고 및 추적 |
| **Sub-task** | Task를 더 작게 분할 |
| **Sprint** | 일정 기간(1~4주) 내 완료할 작업 묶음 (스크럼) |
| **Kanban** | 진행 상태별 열(Column)로 작업 흐름을 시각화 |

#### 2-2. 가입 및 초기 설정

**Step 1 — Atlassian 계정 생성**

```
1. https://www.atlassian.com 접속
2. [Get it free] 또는 https://id.atlassian.com/signup 접속
3. 이메일 입력 → [Continue]
4. 이름, 비밀번호 설정 → [Sign up]
5. 이메일 인증 완료
```

**Step 2 — Jira Software 무료 사이트 생성**

```
1. https://www.atlassian.com/software/jira 접속 → [Get it free]
2. 사이트 이름 입력 (예: myteam → myteam.atlassian.net)
3. 팀 규모 선택 → [Agree and sign up]
4. 무료 플랜 확인 (최대 10명, 기본 기능)
```

**Step 3 — 첫 프로젝트 생성**

```
1. Jira 대시보드 → [Create project]
2. 프로젝트 유형 선택:
   ┌─────────────────────────────────────────────────────┐
   │ Software development (소프트웨어 개발)               │
   │   ├── Scrum     — 스프린트 + 번다운 차트 + 백로그    │
   │   └── Kanban    — 연속 흐름 + WIP 제한 + 칸반 보드   │
   │                                                     │
   │ Business (비즈니스)                                  │
   │   └── Project management — 일반 작업 관리            │
   └─────────────────────────────────────────────────────┘
3. 프로젝트 이름·키(영문 약자) 입력
4. [Create project]
```

#### 2-3. 칸반 보드 상세 사용법

**칸반(Kanban)이란?** 일본 도요타 생산 방식에서 유래한 시각적 작업 흐름 관리 방법론입니다. 진행 중인 작업(WIP)을 제한해 병목을 방지하고 흐름을 최적화합니다.

```
칸반 보드 기본 구조:

┌──────────────┬──────────────┬──────────────┬──────────────┐
│   To Do      │ In Progress  │   In Review  │     Done     │
│  (할 일)     │  (진행 중)   │  (검토 중)   │  (완료)      │
├──────────────┼──────────────┼──────────────┼──────────────┤
│ ○ 로그인 API │ ○ 회원가입   │ ○ DB 스키마  │ ○ 환경 구성  │
│   #PROJ-12   │   #PROJ-8    │   #PROJ-5    │   #PROJ-1    │
│              │              │              │              │
│ ○ 대시보드UI │ ○ JWT 토큰   │              │ ○ Git 설정   │
│   #PROJ-15   │   #PROJ-9    │              │   #PROJ-2    │
│              │              │              │              │
│              │ WIP 제한: 3  │ WIP 제한: 2  │              │
└──────────────┴──────────────┴──────────────┴──────────────┘
```

**보드 열(Column) 커스터마이징**

```
1. 보드 우측 상단 [Board settings] → [Columns]
2. [Add column] 으로 열 추가
3. 각 열에 이슈 상태 매핑
4. WIP(Work In Progress) 제한 설정:
   - 각 열에 최대 동시 작업 수 설정
   - WIP 초과 시 시각적 경고 표시
   - 제약을 통해 병목 지점 식별 가능
```

**이슈 생성 및 관리**

```
이슈 생성:
  보드에서 [+ Create issue] → 제목 입력 (빠른 생성)
  또는 [Create] 버튼 → 상세 폼 (담당자, 우선순위, 레이블, 첨부파일 등)

이슈 이동:
  카드를 드래그 → 다른 열로 이동 (상태 자동 변경)
  또는 이슈 클릭 → Status 필드 클릭 → 상태 선택

이슈 우선순위:
  🔴 Highest (최고)   🟠 High (높음)
  🟡 Medium (중간)    🔵 Low (낮음)   ⚪ Lowest (최저)
```

**JQL(Jira Query Language) — 이슈 검색**

```jql
-- 내 이슈 중 진행 중인 것
assignee = currentUser() AND status = "In Progress"

-- 이번 스프린트 미완료 이슈
sprint in openSprints() AND status != Done

-- 지난 7일간 생성된 버그
issuetype = Bug AND created >= -7d

-- 우선순위 높은 미완료 이슈 (담당자순 정렬)
priority in (High, Highest) AND status != Done ORDER BY assignee ASC

-- 특정 에픽 하위 이슈
"Epic Link" = PROJ-100

-- 레이블로 필터링
labels = "backend" AND status = "In Progress"
```

**자동화 규칙(Automation) 설정**

```
프로젝트 설정 → Automation → [Create rule]

예시 1: PR 생성 시 이슈 자동 전환
  Trigger: Pull request created
  Condition: Issue matches JQL (status = "To Do")
  Action: Transition issue → "In Progress"

예시 2: PR 머지 시 이슈 완료
  Trigger: Pull request merged
  Action: Transition issue → "Done"

예시 3: 기한 초과 자동 알림
  Trigger: Scheduled (매일 오전 9시)
  Condition: Issue matches (due < now() AND status != Done)
  Action: Send email to assignee
```

#### 2-4. GitHub 연동

```
1. Jira 프로젝트 → Project settings → Integrations → GitHub
   또는 Atlassian Marketplace → GitHub for Jira 앱 설치

2. 커밋 메시지에 이슈 키 포함 → 자동 연결
   git commit -m "feat: 로그인 API 구현 PROJ-12"

3. 연결 효과:
   - Jira 이슈 화면에 관련 커밋·브랜치·PR 자동 표시
   - PR 제목에 이슈 키 포함 → 이슈 상태 자동 전환 가능
```

#### 2-5. Jira 플랜 비교

| 플랜 | 가격 | 사용자 | 주요 기능 |
|------|------|--------|----------|
| **Free** | 무료 | 최대 10명 | 칸반·스크럼 보드, 백로그, 로드맵(기본) |
| **Standard** | $8.15/사용자/월 | 무제한 | 고급 권한, 감사 로그, 9~5 지원 |
| **Premium** | $16/사용자/월 | 무제한 | AI 기능, 고급 로드맵, 24/7 지원, 샌드박스 |
| **Enterprise** | 맞춤 | 무제한 | 무제한 사이트, SSO, IP 화이트리스트 |

> **교육·스타트업 팀 권장:** Free 플랜으로 시작 → 10명 초과 또는 고급 기능 필요 시 Standard 업그레이드

---

### 3. Microsoft Azure DevOps

Azure DevOps는 Microsoft가 제공하는 **All-in-One DevOps 플랫폼**입니다. Git 저장소, CI/CD 파이프라인, 칸반 보드, 아티팩트 저장소, 테스트 관리를 모두 포함합니다.

#### 3-1. 핵심 구성 요소 (5개 서비스)

```
Azure DevOps Organization
  └── Project
        ├── Azure Boards   — 이슈 트래킹, 칸반, 스크럼, 로드맵
        ├── Azure Repos    — Git/TFVC 소스 코드 저장소
        ├── Azure Pipelines— CI/CD 파이프라인 (무료 1,800분/월)
        ├── Azure Test Plans — 수동·자동화 테스트 관리
        └── Azure Artifacts— npm, Maven, NuGet, PyPI 패키지 피드
```

| 서비스 | 설명 | 무료 한도 |
|--------|------|----------|
| **Azure Boards** | 칸반·스크럼·Epic·Story·Task 관리 | 무제한 (5명 이하 무료) |
| **Azure Repos** | 프라이빗 Git 저장소 | 무제한 저장소·용량 |
| **Azure Pipelines** | 빌드·테스트·배포 파이프라인 | 1,800분/월 (Linux/Windows) |
| **Azure Test Plans** | 테스트 케이스·실행 관리 | Basic+Test Plans $52/사용자/월 |
| **Azure Artifacts** | 패키지 저장소 | 2 GB 무료 |

#### 3-2. 가입 및 초기 설정

**Step 1 — Microsoft 계정 생성**

```
1. https://account.microsoft.com 접속
   또는 https://outlook.com → 계정 없음? [새 계정 만들기]
2. 이메일 주소 입력 (기존 이메일 사용 가능) 또는 새 Outlook 이메일 생성
3. 비밀번호 설정 → 이름 입력 → 국가/생년월일 입력
4. 보안 코드 인증 완료
```

**Step 2 — Azure DevOps 조직 생성**

```
1. https://dev.azure.com 접속
2. Microsoft 계정으로 로그인
3. [Start free] 클릭
4. [New organization] (또는 자동으로 조직 생성 화면 이동)
5. 조직 이름 입력 (예: myteam → dev.azure.com/myteam)
6. 지역 선택: East Asia (한국에서 가장 가까움)
7. [Continue] → 조직 생성 완료
```

**Step 3 — 첫 프로젝트 생성**

```
1. 조직 대시보드 → [New project]
2. 프로젝트 이름 입력
3. 가시성: Private (비공개) 또는 Public (공개)
4. Advanced 설정:
   - Version control: Git (권장) 또는 TFVC
   - Work item process: Agile / Scrum / CMMI / Basic
     → Scrum: 스프린트·번다운 차트 중심
     → Agile: Epic·Feature·Story·Task 계층 (일반적)
     → Basic: 단순 To Do/Doing/Done 3단계
5. [Create] → 프로젝트 생성 완료
```

#### 3-3. Azure Boards — 칸반 & 스크럼 사용법

**Work Item 계층 구조 (Agile 프로세스 기준)**

```
Epic (대규모 기능)
  └── Feature (기능 단위)
        └── User Story (사용자 스토리)
              └── Task (작업 단위)
              └── Bug (버그)
                    └── Test Case (테스트 케이스)
```

**칸반 보드 설정 및 사용**

```
1. 프로젝트 → Boards → [Boards] (칸반 뷰)
2. 기본 열: Active → Resolved → Closed
   커스터마이즈: [Board settings] (우측 상단 톱니바퀴)
     → Columns 탭 → Add Column / 이름 변경
     → WIP 제한 설정 (각 열 최대 작업 수)

3. Work Item 생성:
   보드 상단 [+ New item] → 제목 입력 → Enter
   또는 Backlog → [+ New Work Item] → 유형·제목 입력

4. 카드 이동:
   드래그 앤 드롭으로 열 이동
   또는 카드 클릭 → State 필드 변경

5. 태그·레이블 추가:
   Work Item 상세 → Tags 필드 → 태그 입력
   보드에서 [Filter] → 태그로 필터링
```

**스프린트(Sprint) 설정**

```
1. Project settings → Boards → Team configuration → Iterations
2. [New child] → 스프린트 이름 (예: Sprint 1), 시작·종료일 설정
3. Backlog 화면 → 이슈를 스프린트로 드래그
4. [Sprints] 뷰 → 스프린트 번다운 차트 자동 생성
```

#### 3-4. Azure Repos — Git 저장소 사용법

```bash
# 저장소 클론
git clone https://myteam@dev.azure.com/myteam/MyProject/_git/MyRepo
# 패스워드: Azure DevOps PAT 사용

# PAT 발급
# User settings (우측 상단 아이콘) → Personal access tokens
# → [New Token] → 이름, 만료일, 권한 설정 → [Create]
# 권한 선택: Code(Read & write), Work Items(Read & write)

# 브랜치 전략 (기본값: main)
git checkout -b feature/PROJ-42-login-api
git add .
git commit -m "feat: 로그인 API 구현 #42"
git push origin feature/PROJ-42-login-api

# Pull Request 생성
# Azure Repos → Pull requests → [New pull request]
# → 소스 브랜치 선택 → 대상 브랜치(main) → 리뷰어 지정 → [Create]
```

**Branch Policy 설정 (코드 품질 게이트)**

```
1. Repos → Branches → main 브랜치 옆 [...] → Branch policies
2. 설정 가능 정책:
   ✅ Require a minimum number of reviewers (최소 리뷰어 수)
   ✅ Check for linked work items (이슈 연결 필수)
   ✅ Check for comment resolution (모든 댓글 해결 후 병합)
   ✅ Build validation (CI 파이프라인 통과 필수)
   ✅ Require merge strategy: Squash merge / Rebase
```

#### 3-5. Azure Pipelines — CI/CD 파이프라인

```yaml
# azure-pipelines.yml (저장소 루트에 배치)
trigger:
  branches:
    include:
      - main

pool:
  vmImage: ubuntu-latest

variables:
  PYTHON_VERSION: '3.11'

stages:
  - stage: Build
    displayName: 빌드 & 테스트
    jobs:
      - job: Test
        steps:
          - task: UsePythonVersion@0
            inputs:
              versionSpec: $(PYTHON_VERSION)

          - script: |
              pip install -r requirements.txt
              pytest tests/ --junitxml=junit.xml --cov=. --cov-report=xml
            displayName: 테스트 실행

          - task: PublishTestResults@2
            inputs:
              testResultsFormat: JUnit
              testResultsFiles: junit.xml

          - task: PublishCodeCoverageResults@1
            inputs:
              codeCoverageTool: Cobertura
              summaryFileLocation: coverage.xml

  - stage: Deploy
    displayName: 프로덕션 배포
    dependsOn: Build
    condition: succeeded()
    jobs:
      - deployment: DeployProd
        environment: production
        strategy:
          runOnce:
            deploy:
              steps:
                - script: |
                    echo "배포 스크립트 실행"
                    # AWS CLI, kubectl, docker push 등
                  displayName: 배포 실행
```

```
파이프라인 생성:
1. Pipelines → [New pipeline]
2. 저장소 선택 (Azure Repos Git / GitHub / Bitbucket 등)
3. 파이프라인 구성 선택:
   - Starter pipeline (빈 YAML)
   - 기존 YAML 파일 선택
   - 권장 템플릿 사용 (Python, Node.js, Docker, Kubernetes 등)
4. YAML 편집 → [Save and run]
```

**환경(Environment) 및 승인 게이트**

```
1. Pipelines → Environments → [New environment]
2. 환경 이름: production / staging / development
3. Approvals and checks 설정:
   [Add check] → Approvals
   → 승인자 지정 (사람 또는 팀)
   → Timeout 설정
   → 배포 전 승인 필수화
```

#### 3-6. GitHub 연동 및 Azure DevOps Boards

기존에 GitHub을 사용하는 팀은 저장소는 GitHub에 두고 Boards + Pipelines만 Azure DevOps로 사용할 수 있습니다.

```
Azure Boards + GitHub 연동:
1. Organization settings → GitHub connections
2. [Connect your GitHub account]
3. GitHub App 설치 → 저장소 권한 부여

커밋 메시지 연결:
  git commit -m "fix: 버그 수정 AB#42"
  → AB#42 가 Azure Boards Work Item #42 와 자동 연결

GitHub Actions → Azure Pipelines 연동:
```

```yaml
# .github/workflows/deploy.yml
name: Deploy to Azure

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Azure Login
        uses: azure/login@v1
        with:
          creds: ${{ secrets.AZURE_CREDENTIALS }}

      - name: Deploy to Azure Web App
        uses: azure/webapps-deploy@v2
        with:
          app-name: my-web-app
          package: .
```

#### 3-7. Azure DevOps 플랜 비교

| 플랜 | 가격 | 포함 내용 |
|------|------|----------|
| **Free** | 무료 | 5명 Basic, Pipelines 1,800분/월, Artifacts 2GB |
| **Basic** | $6/사용자/월 | Boards + Repos + Pipelines (무제한) |
| **Basic + Test Plans** | $52/사용자/월 | Basic + 테스트 관리 도구 |
| **Visual Studio 구독** | $45~$250/월 | VS 라이선스 포함, Azure DevOps 자동 포함 |

> **학생·스타트업:** https://azure.microsoft.com/ko-kr/free → Azure 무료 계정 ($200 크레딧 + 12개월 무료 서비스)

---

### 4. 세 도구 통합 활용 패턴

팀 규모와 기술 스택에 따라 도구를 조합하는 방법입니다.

#### 패턴 A — AWS 중심 팀 (이 과정 권장)

```
소스 코드: GitHub (익숙함 + 오픈소스 생태계)
이슈 트래킹: Jira Free (칸반 + 에픽 관리)
CI/CD: AWS CodePipeline + CodeBuild
배포: AWS CodeDeploy → ECS / Lambda / EKS
패키지: AWS CodeArtifact

GitHub ←→ Jira (커밋 메시지로 이슈 연결)
GitHub ←→ CodePipeline (웹훅으로 빌드 트리거)
```

#### 패턴 B — 소규모 팀 All-in-One (입문 권장)

```
AWS CodeCatalyst 단독 사용
  ├── 소스: 내장 Git 저장소 또는 GitHub 연동
  ├── CI/CD: Workflow YAML
  ├── 이슈: 내장 Issues
  └── 개발환경: Dev Environment (클라우드 IDE)

장점: 단일 플랫폼, AWS 계정 하나로 관리
단점: Jira 대비 이슈 트래킹 기능 제한적
```

#### 패턴 C — Microsoft 생태계 팀

```
소스 코드: Azure Repos (또는 GitHub)
이슈 트래킹: Azure Boards
CI/CD: Azure Pipelines
패키지: Azure Artifacts
배포: Azure App Service / AKS / Azure Functions

GitHub Actions → Azure 배포 (azure/login + webapps-deploy)
```

#### 패턴 D — 교육·학습 환경 (이 과정 실습)

```
Phase 1 (입문):
  GitHub + Jira Free 칸반 → 이슈 트래킹 + PR 관리

Phase 2 (심화):
  GitHub + AWS CodePipeline
  → 코드 푸시 → 자동 빌드 → ECS/Lambda 배포

Phase 3 (통합):
  CodeCatalyst 또는 Azure DevOps
  → All-in-One DevOps 파이프라인 경험
```

#### 워크플로우 흐름도

```mermaid
flowchart TD
    A[이슈 생성\nJira / Azure Boards\n / CodeCatalyst] --> B[브랜치 생성\ngit checkout -b feature/ISSUE-ID]
    B --> C[개발 작업\nVS Code / Dev Environment]
    C --> D[커밋 + 푸시\ngit commit -m 'feat: 기능 ISSUE-42']
    D --> E[PR / MR 생성\nGitHub / Azure Repos]
    E --> F[CI 파이프라인 자동 실행\nCodePipeline / Azure Pipelines\n / GitHub Actions]
    F --> G{테스트 통과?}
    G -->|실패| H[코드 수정 → 재푸시]
    H --> F
    G -->|성공| I[코드 리뷰\n팀원 Approve]
    I --> J[PR 병합\nmain 브랜치]
    J --> K[CD 파이프라인\n자동 배포]
    K --> L[이슈 자동 완료\nDone / Closed]
    L --> M((배포 완료\n다음 이슈로)]
```

---

### 5. 도구별 핵심 단축키 & CLI 요약

**Jira 단축키**

| 단축키 | 기능 |
|--------|------|
| `C` | 새 이슈 생성 |
| `G` + `B` | 보드로 이동 |
| `G` + `I` | 백로그로 이동 |
| `?` | 단축키 목록 표시 |
| `/` | 이슈 검색 |

**Azure DevOps CLI**

```bash
# Azure CLI + DevOps 확장 설치
pip install azure-cli
az extension add --name azure-devops

# 로그인
az devops login --organization https://dev.azure.com/myorg

# Work Item 생성
az boards work-item create \
  --type "User Story" \
  --title "로그인 API 구현" \
  --project MyProject

# 파이프라인 실행
az pipelines run --name "main-pipeline" --project MyProject

# PR 생성
az repos pr create \
  --repository MyRepo \
  --source-branch feature/login \
  --target-branch main \
  --title "feat: 로그인 API 구현"
```

**AWS CLI — CodePipeline 관리**

```bash
# 파이프라인 목록 조회
aws codepipeline list-pipelines

# 파이프라인 실행 시작
aws codepipeline start-pipeline-execution --name MyPipeline

# 파이프라인 실행 상태 확인
aws codepipeline get-pipeline-state --name MyPipeline

# CodeBuild 빌드 로그 확인
aws codebuild list-builds-for-project --project-name MyProject
aws codebuild batch-get-builds --ids <build-id>
```

---

## <i class="fa-solid fa-tv"></i> 관련 유튜브 동영상

아래 링크를 클릭하면 유튜브에서 관련 동영상을 검색할 수 있습니다.

- <i class="fa-solid fa-magnifying-glass"></i> [개발환경 기본 설정 검색](https://www.youtube.com/results?search_query=개발환경+기본+설정)
- <i class="fa-solid fa-magnifying-glass"></i> [PowerShell 개발환경 구성 검색](https://www.youtube.com/results?search_query=PowerShell+개발환경+구성)
- <i class="fa-solid fa-magnifying-glass"></i> [WSL2 개발환경 설정 검색](https://www.youtube.com/results?search_query=WSL2+개발환경+설정)
- <i class="fa-solid fa-magnifying-glass"></i> [Git GitHub 사용법 검색](https://www.youtube.com/results?search_query=Git+GitHub+사용법)
- <i class="fa-solid fa-magnifying-glass"></i> [Node.js Python Java 개발환경 검색](https://www.youtube.com/results?search_query=Node.js+Python+Java+개발환경)
- <i class="fa-solid fa-magnifying-glass"></i> [GitHub Copilot AI 코딩 검색](https://www.youtube.com/results?search_query=GitHub+Copilot+AI+코딩)

---

# 💻 RTX 3080 노트북 GPU 상태 진단 및 AI 개발 최적화 가이드

## 1. 현재 시스템 상태 분석 (Fact Check)
사용자가 제공한 `nvidia-smi` 출력 데이터를 기반으로 분석한 현재 GPU의 사양 및 상태입니다.

| 항목 | 상세 내용 | 상태 및 진단 |
| :--- | :--- | :--- |
| **GPU 모델** | NVIDIA GeForce RTX 3080 Laptop GPU | 정상 인식 완료 |
| **VRAM (비디오 메모리)** | **8,192 MiB (8GB)** | 로컬 모델 학습 및 경량 LLM 추론에 적합 |
| **드라이버 버전** | 576.02 | **최신 상태** |
| **CUDA 버전** | 12.9 | **최신 상태** (최신 AI 프레임워크와 호환성 우수) |
| **최대 전력 (TGP)** | **87W** | 노트북 제조사 설정 사양 확인 |
| **현재 부하량 / 전력 / 온도** | 0% / 25W / 54°C | 대기 상태 (Idle). 연산이 수행되지 않고 있음 |

---

## 2. VS Code AI 개발 시 GPU 실시간 모니터링 방법
AI 학습이나 추론 코드를 실행할 때, 윈도우 작업 관리자는 CUDA 연산량을 정확히 반영하지 못할 수 있습니다. VS Code 터미널에서 다음 명령어를 통해 실시간으로 검증해야 합니다.

### 🔍 실시간 모니터링 명령어 (1초 주기로 갱신)
```bash
nvidia-smi -l 1


---

## 부록: Java OpenJDK 상세 설치 가이드 (Windows)

### 설치 목적
- Java 애플리케이션 빌드·실행을 위한 JDK 설치
- `JAVA_HOME` 환경 변수 등록으로 Maven, IDE 등 다른 도구에서 JDK를 자동 인식

### A-1) jdk.java.net 접속 및 다운로드

1. 브라우저에서 아래 주소 접속
   - https://jdk.java.net/17/
2. **RI Binary** 섹션의 **Windows 11 x64 Java Development Kit** 링크 클릭하여 `.zip` 파일 다운로드

### 공식 사이트
- https://jdk.java.net/ (OpenJDK Reference Implementation)

![jdk.java.net Java SE 17 다운로드 페이지](images/image.png)

---

### A-2) zip 파일 압축 해제

1. 다운로드된 OpenJDK 17 zip 파일(예: `openjdk-17.x.x_windows-x64_bin.zip`)을 압축 해제 도구로 열기
2. 내부 `jdk-17.x.x` 폴더 확인 (bin, conf, include, jmods, legal, lib, release 포함)

![OpenJDK zip 압축 해제](images/image-1.png)

---

### A-3) JDK 폴더를 C:\jdk17 로 이동

1. 압축 해제된 JDK 폴더를 `C:\jdk17` 이름으로 이동 또는 복사
2. Windows 탐색기에서 `C:\jdk17` 폴더가 생성된 것 확인

![C:\jdk17 폴더 생성 확인](images/image-2.png)

---

### A-4) 시스템 > 정보 > 고급 시스템 설정 열기

1. **Windows 설정** → **시스템** → **정보** 이동
2. 우측 하단 **고급 시스템 설정** 링크 클릭

![Windows 시스템 정보 화면](images/image-3.png)

---

### A-5) 환경 변수(JAVA_HOME) 설정

1. **시스템 속성** 창 → **고급** 탭 → **환경 변수(N)...** 버튼 클릭
2. **시스템 변수** 영역에서 **새로 만들기(W)...** 클릭
   - 변수 이름: `JAVA_HOME`
   - 변수 값: `C:\jdk17`
3. 기존 `Path` 시스템 변수를 선택 → **편집(I)...** 클릭 → `%JAVA_HOME%\bin` 추가
4. **확인** 클릭하여 저장

![환경 변수 설정 창 - 사용자 변수 JAVA_HOME](images/image-4.png)

---

### A-6) 사용자 변수에서 JAVA_HOME 확인

환경 변수 창에서 **사용자 변수(U)** 목록에 `JAVA_HOME = C:\jdk17` (또는 설정한 경로)가 등록되었는지 확인합니다.

![사용자 변수 JAVA_HOME 확인](images/image-5.png)

---

### A-7) 시스템 변수에서 JAVA_HOME 확인

**시스템 변수(S)** 목록에도 `JAVA_HOME` 이 등록되어 있는지 확인합니다.

![시스템 변수 JAVA_HOME 확인](images/image-6.png)

---

### A-8) 설치 확인

새 PowerShell 또는 명령 프롬프트를 열어 아래 명령어로 버전을 확인합니다.

```bash
java --version
javac --version
```

---
# NVIDIA RAG AI 챗봇

**NVIDIA의 RAG AI 챗봇은 기업 데이터를 연결해 정확하고 신뢰성 있는 답변을 제공하는 엔터프라이즈용 솔루션으로, GPU 최적화된 LLM과 NeMo 마이크로서비스를 활용해 대규모 배포가 가능합니다. 개인용 웹사이트형 서비스가 아니라, 기업 환경에서 자체 구축하는 형태입니다.**

---

## 📌 개요
- **[Retrieval-Augmented Generation (RAG)](ca://s?q=Retrieval_Augmented_Generation_설명)**: LLM이 학습된 데이터 외에 **기업 내부 데이터베이스·문서·파일을 검색**하여 최신 정보를 결합해 답변 생성.  
- **[NVIDIA NeMo](ca://s?q=NVIDIA_NeMo_설명)**: 데이터 검색·임베딩·추론을 GPU 최적화된 방식으로 처리하는 마이크로서비스.  
- **[Nemotron 모델](ca://s?q=NVIDIA_Nemotron_모델)**: RAG 파이프라인에서 답변 생성을 담당하는 대규모 언어 모델.  
- **[NIM Operator](ca://s?q=NVIDIA_NIM_Operator_설명)**: 쿠버네티스 환경에서 RAG 챗봇을 손쉽게 배포·운영할 수 있도록 지원.  

---

## ⚙️ 주요 기능
- **엔터프라이즈 데이터 연결**: PDF, DOCX, 이미지, 오디오·비디오 등 다양한 포맷 인덱싱 가능.  
- **멀티모달 지원**: 텍스트뿐 아니라 **표, 차트, 이미지, 영상**까지 분석해 답변 생성.  
- **보안성 강화**: **NVIDIA Confidential Computing**으로 기업 데이터 보호.  
- **확장성**: GPU 가속을 통한 대규모 동시 사용자 지원.  
- **OpenAI 호환 API**: 기존 챗봇 프레임워크와 쉽게 통합 가능.  

---

## 🚀 배포 방식
- **Docker**: 단일 GPU 환경에서 빠른 테스트 및 배포.  
- **Kubernetes + Helm**: 대규모 클러스터 환경에서 운영.  
- **OpenShift**: 엔터프라이즈급 배포 지원.  
- **Python 패키지**: 개발자가 직접 코드에서 RAG 기능 호출 가능.  

---

## 📊 ChatRTX vs RAG AI 챗봇

| **[ChatRTX](ca://s?q=NVIDIA_ChatRTX_설명)** | **[RAG AI 챗봇](ca://s?q=NVIDIA_RAG_AI_챗봇)** |
|--------------------------------|--------------------------------|
| 개인용, RTX GPU 필요 | 기업용, 서버·클러스터 환경 필요 |
| 로컬 PC에서 실행 | 클라우드·온프레미스 배포 가능 |
| 개인 문서 기반 맞춤형 챗봇 | 기업 데이터 기반 지식 어시스턴트 |
| 무료 데모 성격 | NVIDIA AI Enterprise 라이선스 필요 |
| 설치 용량 큼 (수십 GB) | 대규모 GPU·스토리지 요구 (~200GB 이상) |

---

## ⚠️ 고려사항
- **개인 사용자는 [ChatRTX](ca://s?q=NVIDIA_ChatRTX_설명)가 적합**, RAG 챗봇은 기업 환경에서만 활용 가능.  
- **RAG 챗봇 구축에는 상당한 하드웨어 자원과 엔터프라이즈 라이선스가 필요**.  
- **첫 배포 시 모델 다운로드에 15~70분 소요**, 이후 캐시로 빠르게 실행 가능.  


---

## 부록: Java 프로젝트 (lab03-java-app) 실행 방법

### 1. 저장소 클론

```bash
git clone https://github.com/edumgt/java-education-001.git
cd java-education-001
```

### 2. Java 버전 확인

```bash
java --version
```

### 3. Maven 빌드

```bash
mvn clean package
```

### 기술 스택

| 구성 요소 | 상세 |
|-----------|------|
| Language | Java 17+ |
| Build Tool | Maven |
| Logging | Log4j2 |
| IDE/Editor | VS Code |
| Version Control | Git + GitHub |
