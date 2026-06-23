# 역할 분리 에이전트 체계 (검증자 2인)

사진의 master·cso·worker·reviewer 구조를 Claude 서브에이전트로 재현.
AI는 Claude 단일이나, 역할 분리·교차 검증 효과는 동일.

## 역할 구성

| 역할 | 구현 | 담당 |
|------|------|------|
| master | 메인 Claude (교수님과 직접 대화) | 작업 접수·분배·최종 보고 |
| cso | `.claude/agents/cso.md` | 전략·작업 분해·방향 점검 |
| worker | `.claude/agents/worker.md` | 실제 결과물 생산 |
| reviewer-A | `.claude/agents/reviewer-a.md` | 검증: 내용·논리·근거 |
| reviewer-B | `.claude/agents/reviewer-b.md` | 검증: 형식·표현·규칙 |

## 작업 흐름

```
교수님 요청
   │
 master(메인) ── 필요 시 ── cso : 작업 분해·전략
   │
 worker : 결과물 생산
   │
 reviewer-A + reviewer-B 동시 검증 (관점 분리 → 교차 검증)
   │
 master : 검증 반영·통합 → 교수님 보고
```

## 검증자 2인의 관점 분리

- reviewer-A = 내용·논리·근거 (사실·인용·논지)
- reviewer-B = 형식·표현·규칙 (구조·문체·APA·줄표)

두 관점이 겹치지 않아 한 명이 놓친 오류를 다른 한 명이 잡는다.
둘 다 "통과"여야 master가 최종 확정. 하나라도 "수정필요"면 worker 재작업.

## 사용 방법 (교수님)

평소처럼 작업을 지시하면 master(메인 Claude)가 위 흐름을 자동 운용.
"검증 강하게" 요청 시 reviewer 2인 검증을 명시적으로 실행.
역할을 끄고 싶으면 "혼자 처리해" 라고 지시.
