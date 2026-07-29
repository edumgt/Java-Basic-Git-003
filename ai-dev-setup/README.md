# VS Code · Claude Code · Codex · Docker AI 개발 환경 가이드

> Windows + WSL2, macOS, Linux에서 이 저장소의 Python/Node/Java 실습과 로컬 AI·RAG 실습을 시작하기 위한 안내입니다. 명령은 특별한 언급이 없으면 **WSL2 또는 Linux/macOS 터미널**에서 실행합니다.

## 1. 완성 형태와 빠른 시작

```text
VS Code (Remote - WSL / Docker 확장)
 ├─ Claude Code 확장  ─ Anthropic 계정으로 로그인
 ├─ Codex 확장        ─ ChatGPT 계정으로 로그인
 └─ 통합 터미널
      └─ Docker Compose
           ├─ Ollama       : 로컬 LLM API
           ├─ Qdrant       : 벡터 DB (RAG)
           ├─ PostgreSQL   : pgvector 포함 관계형 DB
           └─ Playwright   : 웹 UI 자동화/테스트
```

처음에는 아래 순서만 따라 하면 됩니다.

1. VS Code와 Docker Desktop을 설치하고, Windows라면 Docker Desktop의 **WSL Integration**을 켭니다.
2. 이 저장소를 WSL 홈 디렉터리 아래에 복제한 뒤 `code .`로 엽니다.
3. VS Code에 Claude Code, Codex, Docker, Remote - WSL 확장을 설치하고 각각 로그인합니다.
4. 최소 AI/RAG 컨테이너를 실행하고 Ollama 모델을 하나 받습니다.

```bash
git clone https://github.com/edumgt/edumgt-lab-init.git
cd edumgt-lab-init
code .

# 아래 "7. 최소 AI/RAG 컨테이너"의 명령을 이어서 실행
```

## 2. 운영체제별 사전 준비

### Windows 10/11 + WSL2 (권장)

1. 관리자 PowerShell에서 WSL2와 Ubuntu를 설치하고 재부팅합니다.

   ```powershell
   wsl --install -d Ubuntu
   wsl --update
   wsl -l -v
   ```

   `Ubuntu`의 `VERSION`이 `2`인지 확인합니다. 가상화 오류가 발생하면 BIOS/UEFI의 Intel VT-x 또는 AMD-V를 활성화합니다.

2. Microsoft Store 또는 [VS Code 공식 사이트](https://code.visualstudio.com/)에서 VS Code를 설치합니다.
3. [Docker Desktop](https://www.docker.com/products/docker-desktop/)을 설치할 때 **Use WSL 2 based engine**을 선택합니다.
4. Docker Desktop → **Settings → Resources → WSL Integration**에서 Ubuntu를 활성화하고 **Apply & restart** 합니다.
5. Ubuntu 터미널에서 설치를 확인합니다.

   ```bash
   docker --version
   docker compose version
   docker run --rm hello-world
   ```

프로젝트는 `/mnt/c/...`보다 WSL 파일시스템(예: `~/workspace/edumgt-lab-init`)에 두는 편이 파일 감시와 볼륨 성능 면에서 유리합니다.

### macOS / Linux

- macOS는 Docker Desktop을 설치한 뒤 터미널에서 `docker run --rm hello-world`를 실행합니다.
- Ubuntu 등 Linux는 [Docker Engine 공식 설치 문서](https://docs.docker.com/engine/install/)의 배포판별 절차를 따릅니다. 설치 후 현재 사용자가 `docker` 그룹을 쓸 수 있게 설정하고, 새 터미널을 열어 확인합니다.

  ```bash
  sudo usermod -aG docker "$USER"
  newgrp docker
  docker run --rm hello-world
  ```

> `docker` 그룹은 Docker 데몬에 사실상 관리자 권한으로 접근할 수 있습니다. 공용 서버에서는 관리자 정책에 맞게 사용하세요.

## 3. VS Code 필수 확장팩

VS Code의 Extensions 화면(`Ctrl+Shift+X`)에서 아래 확장을 설치합니다. `code` 명령이 PATH에 등록되어 있다면 한 번에 설치할 수도 있습니다.

```bash
code --install-extension ms-vscode-remote.remote-wsl
code --install-extension ms-azuretools.vscode-docker
code --install-extension ms-vscode-remote.remote-containers
code --install-extension ms-python.python
code --install-extension ms-toolsai.jupyter
code --install-extension redhat.vscode-yaml
```

| 확장 | 용도 |
|---|---|
| Remote - WSL | Windows의 VS Code UI와 WSL의 Linux 개발 도구를 연결 |
| Docker | 컨테이너·이미지·Compose 로그를 VS Code에서 관리 |
| Dev Containers | 프로젝트 자체를 컨테이너 안에서 열 때 사용 |
| Python / Jupyter | Python, 노트북, 가상환경 개발 |
| YAML | Compose/Kubernetes YAML 편집 보조 |

Windows에서 프로젝트 폴더를 열 때 왼쪽 아래의 원격 표시가 `WSL: Ubuntu`인지 확인합니다. 아니라면 명령 팔레트(`Ctrl+Shift+P`)에서 **WSL: Reopen Folder in WSL**을 실행합니다.

## 4. Claude Code를 VS Code에 설치·연동

Claude Code 확장은 VS Code 안에서 계획 검토, 파일 참조, diff 승인, 대화 이력을 제공합니다. 확장 자체는 CLI를 포함하므로 확장만 사용할 경우 별도의 `claude` CLI 설치가 필요하지 않습니다.

1. VS Code Extensions에서 **Claude Code**를 검색하고 게시자가 **Anthropic**인 확장을 설치합니다.
   - CLI 설치가 가능한 환경에서는 다음도 사용할 수 있습니다.

     ```bash
     code --install-extension anthropic.claude-code
     ```

2. 파일을 하나 연 다음 편집기 오른쪽 위 또는 Activity Bar의 ✦ 아이콘을 눌러 Claude 패널을 엽니다.
3. 브라우저에서 Claude 계정으로 로그인합니다. 유료 Claude 구독(Pro/Max/Team/Enterprise) 또는 Anthropic Console 계정을 사용할 수 있습니다. Console/API 방식은 조직의 과금 정책을 먼저 확인합니다.
4. 첫 작업은 읽기 전용으로 요청합니다.

   ```text
   이 저장소의 구조와 실행 방법을 분석해 줘. 파일을 수정하거나 명령을 실행하기 전에는 계획과 이유를 먼저 보여 줘.
   ```

### 권한 모드와 파일 컨텍스트

- **Manual**: 파일 변경과 대부분의 명령을 매번 승인합니다. 처음 사용하는 저장소의 기본값으로 권장합니다.
- **Plan**: 실행 전 계획을 Markdown으로 검토합니다. 여러 파일을 바꾸는 작업에 적합합니다.
- **Edit automatically**: 파일 편집을 자동 승인합니다. 테스트·lint가 안정화된 뒤에만 사용합니다.
- 프롬프트에 `@파일명` 또는 `@폴더명`을 넣으면 필요한 범위만 컨텍스트에 추가할 수 있습니다. 선택 코드에서는 `Alt+K`(Windows/Linux)로 줄 범위를 넣을 수 있습니다.

VS Code 설정에서 `Extensions → Claude Code`를 열어 기본 권한 모드, 패널 위치, `.gitignore` 존중 여부를 조정합니다. `bypass permissions`는 네트워크가 차단된 일회성 샌드박스가 아니라면 사용하지 않습니다.

### 프로젝트 지시 파일: `CLAUDE.md`

프로젝트 루트의 `CLAUDE.md`에는 짧고 검증 가능한 규칙만 둡니다. 비밀값은 절대 넣지 않습니다.

```markdown
# Claude 작업 규칙

- Python 변경 뒤에는 `pytest`를 실행한다.
- 새 의존성 추가 전에는 목적과 대안을 설명한다.
- `.env`, 인증서, 운영 DB 설정은 읽거나 수정하지 않는다.
- 파일을 여러 개 수정하기 전에는 계획을 먼저 제시한다.
```

CLI가 필요하면 [Claude Code 공식 설치 안내](https://code.claude.com/docs/en/setup)를 사용해 설치한 후 VS Code 통합 터미널에서 `claude`를 실행합니다. 확장을 설치해도 `claude` 명령이 PATH에 자동으로 생기지는 않습니다.

## 5. Codex를 VS Code에 설치·연동

Codex 확장은 OpenAI의 VS Code용 코딩 에이전트입니다. 로컬 워크스페이스에서 작업하고, 필요할 때 변경 diff와 명령 실행 권한을 검토할 수 있습니다.

1. Extensions에서 **Codex**를 검색하여 게시자가 **OpenAI**인 확장을 설치합니다.

   ```bash
   code --install-extension openai.chatgpt
   ```

2. Activity Bar의 Codex를 열고 ChatGPT 계정으로 로그인합니다. 조직에서 API 사용을 허용한 경우에는 해당 조직의 인증·비용 정책을 따릅니다.
3. 새 채팅을 만들고 작업 범위와 검증 명령을 명시합니다.

   ```text
   lab01-python-app만 검토해 줘. 변경이 필요하면 먼저 계획을 제시하고,
   변경 후에는 관련 테스트 또는 실행 명령을 알려 줘. .env와 비밀값은 건드리지 마.
   ```

4. 코드나 파일 전체를 선택한 뒤 Command Palette에서 **Codex: Add to Thread** 또는 **Codex: Add File to Thread**를 사용해 필요한 컨텍스트만 전달합니다.

### WSL2에서 Codex 사용

저장소와 도구가 WSL2에 있다면 VS Code 설정에서 `Codex: Run In Windows Subsystem For Linux`를 켭니다. VS Code가 다시 로드된 뒤 Codex가 Linux의 Git, Docker, Python, Node 도구를 사용합니다.

Codex의 공통 설정(모델, 권한, sandbox, MCP 등)은 Codex 패널의 톱니바퀴 → **Codex Settings**에서 확인합니다. VS Code 전용 동작은 일반 VS Code 설정에서 `@ext:openai.chatgpt`로 검색합니다. 변경 작업 전에는 보수적인 권한 모드로 시작하고 diff와 실행 명령을 검토하세요.

### 프로젝트 지시 파일: `AGENTS.md`

Codex는 작업 시작 시 프로젝트 루트부터 현재 디렉터리까지의 `AGENTS.md`를 읽습니다. 다음은 이 저장소에 맞춰 확장할 수 있는 예시입니다.

```markdown
# Repository expectations

- 문서 변경은 Markdown 링크와 명령어가 실제 경로와 일치해야 한다.
- Compose 변경 뒤에는 `docker compose -f infra/docker-compose.yml config`를 실행한다.
- 비밀키, `.env`, 사용자별 절대 경로를 커밋하지 않는다.
- 무관한 파일은 수정하지 않는다.
```

Claude의 `CLAUDE.md`와 Codex의 `AGENTS.md`는 동시에 두어도 됩니다. 공통 규칙은 내용이 어긋나지 않게 유지하고, 각 도구의 고유 설정·워크플로우만 분리하세요.

## 6. 두 에이전트를 함께 쓰는 안전한 흐름

| 단계 | 권장 도구 | 예시 |
|---|---|---|
| 설계·요구사항 검토 | Claude 또는 Codex | 구현 범위·위험·테스트 계획 작성 |
| 한 기능 구현 | 한 번에 **하나의** 에이전트 | 브랜치에서 구현·테스트 실행 |
| 리뷰 | 다른 에이전트 | `git diff` 기준으로 보안·예외·테스트 누락 점검 |
| 반영 | 개발자 | diff, 테스트 결과, `git status`를 확인 후 커밋 |

동일 파일을 두 에이전트가 동시에 자동 편집하게 두지 마세요. 반드시 Git 브랜치 또는 worktree를 나누고, API 키·토큰·개인정보·운영 로그를 채팅에 붙여 넣지 않습니다.

## 7. 이 저장소의 AI/RAG 컨테이너 설치

컨테이너 정의는 [`../infra/docker-compose.yml`](../infra/docker-compose.yml)에 있습니다. Compose 프로필을 사용하므로 필요한 서비스만 실행할 수 있습니다.

| 서비스 | 역할 | 호스트 접속 |
|---|---|---|
| Ollama (`ai`) | 로컬 LLM 서버, OpenAI 호환 개발용 모델 실행 | `http://localhost:11435` |
| Qdrant | 임베딩 벡터 검색 DB | `http://localhost:6333` |
| PostgreSQL + pgvector | 메타데이터·벡터를 함께 저장하는 RAG DB | `localhost:5432` |
| Playwright (`ai`) | 브라우저 자동화·웹 테스트 실행 환경 | Compose 네트워크 내부 |
| Redis | 캐시·작업 큐·세션 저장 | `localhost:6379` |
| MongoDB | 문서형 원본/대화 데이터 저장 | `localhost:27017` |
| Neo4j (`graph`) | 지식 그래프·Graph RAG | `http://localhost:7474` |
| Prometheus/Grafana (`monitoring`) | 컨테이너·앱 메트릭 관찰 | `9090` / `3000` |

### 최소 AI/RAG 구성 (권장)

아래 명령은 학습에 필요한 `PostgreSQL`, `Redis`, `Qdrant`, `Ollama`, `Playwright`만 명시적으로 실행합니다. 기본 Compose 전체를 실행할 때 포함되는 Keycloak 등 다른 서비스는 시작하지 않습니다.

```bash
# 저장소 루트에서 실행
docker compose -f infra/docker-compose.yml --profile ai up -d \
  postgres redis qdrant ollama playwright

# 상태와 로그 확인
docker compose -f infra/docker-compose.yml ps
docker compose -f infra/docker-compose.yml logs -f ollama qdrant
```

첫 모델을 다운로드합니다. 컨테이너 안에서는 서비스 포트 `11434`를 사용하고, PC/WSL에서 호출할 때만 `11435`를 사용합니다.

```bash
# 코딩 실습용 경량 모델 예시
docker exec -it ollama ollama pull qwen2.5-coder:7b
docker exec -it ollama ollama list

# 로컬 API 확인 (호스트/WSL에서 실행)
curl http://localhost:11435/api/tags
curl http://localhost:6333/collections
```

다운로드하는 모델 크기만큼 디스크 공간이 필요합니다. 7B 모델도 수 GB를 사용하므로 `docker system df`와 남은 디스크 공간을 먼저 확인하세요.

### 프로필별 확장 실행

```bash
# 지식 그래프(Neo4j) 추가
docker compose -f infra/docker-compose.yml --profile graph up -d neo4j

# Kafka + NiFi 스트리밍 파이프라인 추가
docker compose -f infra/docker-compose.yml --profile streaming up -d

# Prometheus + Grafana 모니터링 추가
docker compose -f infra/docker-compose.yml --profile monitoring up -d

# 현재 Compose 파일의 구문·변수 치환을 실행 전 검증
docker compose -f infra/docker-compose.yml config >/dev/null
```

중지와 데이터 관리 명령입니다.

```bash
# 컨테이너만 중지·삭제하고 named volume의 데이터는 보존
docker compose -f infra/docker-compose.yml down

# 볼륨까지 삭제: DB·Qdrant·Ollama 데이터가 사라지므로 정말 초기화할 때만 사용
docker compose -f infra/docker-compose.yml down -v
```

### GPU 가속 (선택)

NVIDIA GPU를 쓰려면 호스트에 최신 NVIDIA 드라이버와 [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)이 필요합니다. 설치 후 다음으로 Docker의 GPU 접근을 확인합니다.

```bash
docker run --rm --gpus all nvidia/cuda:12.6.3-base-ubuntu22.04 nvidia-smi
```

기본 Compose는 CPU에서도 동작합니다. GPU 검증이 끝난 뒤에만 GPU override를 함께 적용합니다.

```bash
docker compose -f infra/docker-compose.yml -f infra/docker-compose.gpu.yml \
  --profile ai up -d ollama
```

Ollama 모델은 named volume `ollama_data`에 저장됩니다. 특정 Windows 사용자 경로에 의존하지 않으므로 Windows·WSL·Linux에서 같은 Compose 파일을 사용할 수 있습니다.

## 8. 비밀값·포트·문제 해결

### 비밀값 관리

- `OPENAI_API_KEY`, `ANTHROPIC_API_KEY` 등은 `.env` 또는 OS 환경 변수에만 둡니다. `.env`는 Git에 커밋하지 않습니다.
- 현재 학습용 Compose의 DB 비밀번호와 관리 계정은 예제값입니다. 외부에 공개되는 서버에서는 `.env`로 교체하고 포트를 localhost 또는 사설망으로 제한하세요.
- `docker compose config` 출력이나 AI 채팅에 `.env` 내용이 포함되지 않도록 주의합니다.

저장소의 [`.env.example`](../.env.example)에는 키 이름만 남깁니다. 사용 시에는 이를 복사해 `.env`를 만들고 값을 채웁니다.

```bash
cp .env.example .env
```

### 자주 발생하는 문제

| 증상 | 확인·조치 |
|---|---|
| WSL에서 `docker: command not found` | Docker Desktop의 WSL Integration에서 해당 Ubuntu 배포판을 켠 뒤 WSL/VS Code를 재시작 |
| `port is already allocated` | `docker compose ... ps`, `docker ps`, 해당 포트의 기존 앱을 확인. 충돌 포트를 중지하거나 Compose 포트를 변경 |
| Ollama가 시작되지 않음 | `docker compose ... logs ollama` 확인. GPU 미구성 환경이면 GPU 예약 설정과 NVIDIA Container Toolkit 상태 점검 |
| Claude/Codex 로그인 화면이 반복 | VS Code를 완전히 재시작하고 `Developer: Reload Window` 실행. WSL 환경변수 기반 API 인증이라면 `code .`로 VS Code를 WSL 터미널에서 실행 |
| AI가 너무 많은 파일을 읽음 | `@파일/폴더`와 선택 영역만 제공하고, `.gitignore`·`CLAUDE.md`·`AGENTS.md`에 제외 규칙 명시 |

## 공식 문서

- [Claude Code for VS Code](https://code.claude.com/docs/en/vs-code)
- [OpenAI Codex IDE extension](https://developers.openai.com/codex/ide/)
- [Docker Desktop 설치](https://docs.docker.com/desktop/)
- [Docker Compose profiles](https://docs.docker.com/compose/how-tos/profiles/)
- [Ollama](https://ollama.com/)
- [Qdrant](https://qdrant.tech/documentation/)
