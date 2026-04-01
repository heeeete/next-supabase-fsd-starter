# Supabase Context

## Tables & Schema


## RLS (Row Level Security)

- 모든 테이블 RLS 활성화 (ENABLE ROW LEVEL SECURITY)
- **Read**: Authenticated/Public (정책별 상이)
- **Write**: auth.uid() = user_id 기반 본인 확인 필수
- **Service Role**: 클라이언트 사용 금지, 서버 사이드/Admin 작업 전용

## Storage


## Auth (Client)


## Data Access Rules

- Server: 서버 전용 Supabase 클라이언트 생성 함수 createClient() 사용
- 위치: @src/shared/lib/supabase/server.ts
- 내부적으로 @supabase/ssr + next/headers cookies() 기반으로 동작
- Client: 직접 Supabase 접근은 필요한 경우에만 사용
- 클라이언트 인증 상태 참조는 useAuth() 기준
- 데이터 패칭은 entities/\*\*/api 기준으로 통합
