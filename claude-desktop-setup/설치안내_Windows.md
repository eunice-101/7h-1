# Windows 설치 안내 (그대로 따라 하기)

## 1단계. Claude Code 설치

### 쉬운 방법 (데스크톱 앱)
1. 웹브라우저에서 `claude.ai/code` 접속
2. Windows용 내려받기 → 설치 파일 실행 → 설치
3. 실행 후 Claude 계정으로 로그인

### 또는 CLI 방법 (터미널)
1. Node.js 설치: `nodejs.org` 에서 LTS 버전 내려받아 설치
2. 시작 메뉴 → "PowerShell" 입력 → 실행
3. 아래 한 줄 입력 후 Enter
   ```
   npm install -g @anthropic-ai/claude-code
   ```
4. 설치 후 작업 폴더에서 `claude` 입력하면 시작

---

## 2단계. 설정 폴더 열기

1. 키보드 `윈도우키 + R` 동시에 누르기
2. 나타난 칸에 아래를 붙여넣고 Enter
   ```
   %USERPROFILE%\.claude
   ```
3. `.claude` 폴더가 열립니다.
   (폴더가 없다고 나오면, Claude Code를 한 번 실행하면 자동 생성됩니다.)

---

## 3단계. 파일 복사 (핵심)

`.claude` 폴더 안이 아래처럼 되도록 넣습니다.

```
C:\Users\[사용자이름]\.claude\
├── CLAUDE.md          ← 이 묶음의 CLAUDE.md 를 여기에
└── agents\            ← 이 묶음의 agents 폴더를 통째로 여기에
    ├── cso.md
    ├── worker.md
    ├── reviewer-a.md
    └── reviewer-b.md
```

주의
- 이미 `CLAUDE.md`가 있으면, 기존 내용 끝에 이어 붙이거나 백업 후 교체하세요.
- `agents` 폴더가 이미 있으면 그 안에 4개 파일만 넣으면 됩니다.

---

## 4단계. 최고 성능 설정

1. Claude Code 실행 후 대화창에서 `/model` 입력 → 가장 상위 모델(Opus) 선택
2. 화면이 느리지 않다면 `/fast` 로 빠른 모드도 켤 수 있음(Opus 유지, 출력만 빨라짐)

---

## 5단계. 작동 확인

새 대화창에 이렇게 입력해 보세요.
> "당신의 역할과 지킬 규칙을 한 줄로 요약해줘"

다분야 전담 비서로 답하면 설정 성공입니다.
역할 검증을 시험하려면:
> "이 글 검증 강하게 해줘" → reviewer 2인이 작동하는지 확인

---

## 막히면
설치 중 화면을 캡처해서 다음 대화창에 올리시면, 그 지점부터 다시 안내하겠습니다.
