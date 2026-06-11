# 학원 관리 키오스크 (academy-app)

학원 데스크에 비치하는 **출결 체크 키오스크**입니다. 학생이 본인 전화번호를 입력하면
입실/외출/퇴실을 처리하고, 지각 여부를 자동으로 계산합니다.

> Next.js 14 (App Router) + Supabase(Postgres / Auth / RLS) 기반으로 제작되었습니다.

---

## 주요 기능

- **출결 키오스크 (`/kiosk`)** — 전화번호 키패드로 학생을 조회하고, 현재 상태(미입실 / 입실 중 / 외출 중)에
  따라 입실·외출·복귀·퇴실 액션을 보여줌
- **지각 자동 판정** — 입실 시각과 시간표(`periods`)를 비교해 지각 여부와 지각 시간을 자동 계산
- **외출 관리** — 화장실 / 학원 외출 / 식사 등 외출 유형을 구분해 기록하고 복귀 시 자동 종료 처리
- **역할 기반 로그인 (`/login`)** — 원장(principal) / 강사(teacher) 역할 구분
- **데이터 모델** — 학생, 직원, 시간표, 출결, 외출, 수업 방해 기록, 플래너(태스크) 체크,
  월간 리포트, 공지사항까지 포함한 전체 학원 운영 스키마 설계 (`supabase/schema.sql`)

---

## 기술 스택

| 영역 | 기술 |
| --- | --- |
| Frontend | Next.js 14 (App Router), React 18, TypeScript, Tailwind CSS |
| Backend / DB | Supabase (Postgres, Auth, Row Level Security) |
| 클라이언트 SDK | `@supabase/supabase-js`, `@supabase/ssr` |

---

## 디렉토리 구조

```
app/
├── kiosk/             # 출결 체크 키오스크 (전화번호 키패드 + 액션 패널)
│   ├── page.tsx
│   ├── actions.ts     # 입실/외출/복귀/퇴실 서버 액션
│   └── components/    # Keypad, ActionPanel
├── desk/              # 데스크(직원용) 페이지
└── login/             # 원장/강사 로그인

lib/
├── supabase/          # 서버/클라이언트 Supabase 인스턴스
├── auth.ts            # 인증 유틸
├── hooks/use-staff.ts # 로그인한 직원 정보 훅
└── types.ts           # 학생/직원/출결/외출/시간표 등 도메인 타입

supabase/
├── schema.sql         # 전체 테이블 + RLS 정책
└── seed-staff.sql      # 초기 직원 계정 시드
```

---

## 시작하기

### 1. 의존성 설치

```bash
npm install
```

### 2. 환경변수 설정

`.env.local.example`을 복사해 `.env.local`을 만들고 Supabase 프로젝트의 URL과 anon key를 입력합니다.

```bash
cp .env.local.example .env.local
```

```
NEXT_PUBLIC_SUPABASE_URL=https://<your-project>.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=<your-anon-key>
```

### 3. DB 스키마 적용

Supabase 프로젝트의 SQL Editor에서 `supabase/schema.sql`, `supabase/seed-staff.sql`을 순서대로 실행합니다.

### 4. 개발 서버 실행

```bash
npm run dev
```

[http://localhost:3000](http://localhost:3000) 에서 확인할 수 있습니다.
