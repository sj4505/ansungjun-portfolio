# 가계부 (budget-app)

개인용 가계부 웹앱입니다. 수입/지출을 기록해 Supabase에 저장하고,
Polar 결제 웹훅을 통해 결제 이벤트를 처리합니다.

## 기술 스택

| 영역 | 기술 |
| --- | --- |
| Frontend | Vanilla JS + Tailwind (CDN), 단일 페이지 (`index.html`) |
| Backend | Supabase (Postgres, RLS) |
| 결제 | Polar SDK (`@polar-sh/sdk`), Webhook (`api/webhook/polar.js`) |
| 배포 | Vercel |
| 테스트 | Jest (`tests/webhook.test.js`) |

## 주요 기능

- 수입/지출 입력 및 카테고리별 집계
- Supabase에 데이터 영구 저장 (Row Level Security로 보호)
- Polar 결제 webhook 수신 및 서명 검증

## 실행

```bash
npm install
npm test
```

`index.html`을 정적으로 호스팅하거나 Vercel에 배포해서 사용합니다.
환경변수는 `.env.local.example`을 참고하세요.
