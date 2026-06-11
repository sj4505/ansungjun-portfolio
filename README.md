# 안성준 포트폴리오

AI를 적극적으로 활용해 일상의 문제를 직접 해결하면서 만든 프로젝트들을 모은 레포입니다.
기획과 설계는 직접 진행하고, 구현은 AI에게 맡기는 방식으로 작업했습니다.

## 프로젝트

| 프로젝트 | 설명 | 기술 스택 |
| --- | --- | --- |
| [academy-app](./academy-app) | 학원 관리 키오스크 — 실시간 출결 체크, 플래너 체크, 외출 관리 | Next.js 14, Supabase (Postgres, Auth, RLS) |
| [gwating-app](./gwating-app) | 그룹 과팅 매칭 앱 — 성향 테스트 → 팀 구성 → 자동 매칭 → 팀장 채팅 → 만남 확정 | Next.js 14, Tailwind CSS, Supabase (Postgres, Realtime, RLS), Jest |
| [budget-app](./budget-app) | 개인 가계부 — Polar 결제 웹훅 연동 수입/지출 트래커 | Vanilla JS, Supabase, Polar SDK |
| [focus-flow](./focus-flow) | AI 자기관리 앱 — 포모도로 타이머, AI 플래너, 태스크 분해 | HTML / CSS / JS |

## 작업 방식

각 프로젝트는 기획·설계는 직접 진행하고, 구현은 Claude Code에게 맡기는 방식으로 작업했습니다.
구현이 끝나면 별도의 AI(Codex)가 감사(QA) 역할을 맡아 코드 리뷰를 진행하는 이중 검증
워크플로우를 구성해서 사용하고 있습니다.
