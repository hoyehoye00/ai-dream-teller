# Product Requirments Document(PRD)

## 1. 프로젝트 개요 (Project Overview)
  - **프로젝트 명**: AI DREAM TELLER (AI 꿈 해몽 서비스)
  - **목표**: 사용자가 입력한 꿈 내용을 AI가 분석하여 심층적인 해몽과 조언을 제공하는 수익형 웹 서비스
  - **핵심 가치 1**: 신비롭고 직관적인 UI 경험과 정확도 높은 AI 분석을 통해서 사용자에게 인사이트와 재미 제공.
  - **핵심 가치 2**: 프로이트, 칼 융, 신경과학, 게슈탈트 등 해몽을 맡기고 싶은 전문 분야를 선택해서 해몽 요청 가능. 
 
## 2. 타겟 유저(Target Audience)
  - 꿈의 의미를 검색해보는 습관이 있는 20-40대 남녀.
  - 모바일 환경에서 간편하게 결과를 확인하고 공유하고 싶어하는 유저.

## 3. 기술 스택(Tech Stack)
  - **Web Framework**: Next.js 16.2.10 (App Router)
  - **Language**: TypeScript
  - **Styling**: Tailwind Css, Shadcn/ui
  - **Backend & DB**: Next.js API Routes, Supabase
  - **Payments**: Toss payments
  - **AI**: Gemini with gemini sdk

## 4. 디자인 가이드(Design Guide)
  - **Theme**: Mystical, Vibrant, Fluid
  - **Colors**: Deep Purple, Neon Blue, Soft Pink (Aurora Gradients)
  - **Interactions**: 부드러운 스크롤, 호버 시 빛나는 효과, 로딩 시 몽환적인 애니메이션 

## 5. UX 플로우 (프론트엔드 작업용)

### 5.1 전체 레이아웃
1. 상단 네비게이션바
   - (공통) 홈 로고 
   - (비회원) 로그인, 비회원 주문 조회 
   - (회원) 마이페이지
2. Body 
   - 각 페이지 별 주요 내용 렌더링
3. Footer
   - 사업자 정보, 이용약관 링크, 개인정보처리 방침 링크, 문의하기
4. Head & Meta
   - SEO, Open Graph, GA4 등 Analytics 설정

### 5.2 세부 페이지 구성

1. **메인 랜딩페이지 (/)**
   - 서비스 한줄 소개 
   - 프로덕트 상세로 넘어가는 후킹 버튼(프로덕트 상세 페이지로 이동) 
   - 서비스에 대한 여러 feature 소개 
   - 이미 풀이된 이전 유저들의 꿈 해몽 텍스트 및 AI 이미지 예시 리스트 섹션 (더보기 -> 예시 리스트 피드로 이동)

2. **프로덕트 상세 페이지 (/dream-teller)**
   - 간략한 서비스 사용 소개 
   - 프로이트, 칼 융, 신경과학, 게슈탈트 등 해몽을 맡기고 싶은 전문 분야 선택 
   - 유저의 꿈 입력란 및 꿈 풀이 요청 버튼 
   - 안내 및 주의 사항 
     * 보통 3분 이내에 생성이 완료됩니다. 
     * 꿈 해석은 AI를 통해 정신분석, 신화, 상징학 데이터를 기반으로 생성됩니다. 
     * 이 해석은 자기 이해를 돕기 위한 참고 자료이며, 의학적/심리학적 진단을 대체하지 않습니다. 
   - 구매 옵션 선택 섹션 
     * (기본) 단순 텍스트 해석: 1,500원 
     * (추가 옵션) AI 생성 이미지 추가: +500원

3. **결제 페이지 (/payments)**
   - 영수증 디자인을 참고한 디자인의 결제 페이지 
   - 토스페이먼츠 위젯이 들어갈 섹션 
   - 회원 결제와 비회원 결제 모두 지원 
   - 결제가 성공적으로 완료된 후 회원은 마이페이지, 비회원은 비회원 주문 조회 페이지로 이동 
   - 결제에 실패했을 경우 입력한 꿈 정보가 사라지지 않고 결제 페이지에 그대로 머물러 있음

4. **해석 확인 페이지 (/dream-result/[order-id])**
   - 결제한 유저가 자신의 꿈 해석 및 AI 이미지(옵션)를 확인할 수 있는 페이지 
   - 해몽과 이미지 뿐 아니라 자신이 입력한 꿈 내용도 함께 확인할 수 있어야 함 
   - 다른 사람에게 공유할 수 있도록 링크 카피, 소셜 공유 버튼 섹션 하단 배치 
   - 회원의 경우 캘린더 라이브러리를 활용해 해몽이 이뤄진 날짜에 하이라이트 표시 및 해당 일자를 누를 경우 해당 해몽 결과 페이지로 넘어감

5. **유저의 마이페이지 (/my-page)**
   - 회원 가입된 유저만 자신의 마이페이지 접근 가능 
   - 캘린더 라이브러리를 활용해 해몽이 이뤄진 날짜에 하이라이트 표시 및 해당 일자를 누를 경우 해당 해몽 결과 페이지로 넘어감 
   - 구매 내역 리스트가 캘린더 하단에 배치 및 해당 리스트 아이템을 누를 경우 해당 해몽 결과 확인 페이지로 넘어감 
   - 닉네임(수정 가능 기능), 로그인 한 소셜 서비스(구글 or 카카오) 로고, 이메일 주소, 로그아웃 버튼

6. **비회원 로그인 (/guest-login)**
   - 간단한 페이지 소개 
   - 전화번호 및 비밀번호 입력 폼 
   - 비회원 주문 조회 버튼

7. **비회원 주문 조회 페이지 (/guest-check)**
   - 6번에서 로그인 한 비회원이 자신의 구매 내역을 조회하는 페이지 
   - 구매내역 리스트가 배치되어 있고 해당 리스트 아이템을 눌렀을 때 해당 해몽 결과 확인 페이지로 이동

8. **과거 풀이 내역 리스트 피드 페이지 (/feeds)**
   - 이전 유저들의 과거 풀이 내역 리스트 제공 
   - 페이스북 형태의 피드 디자인 
   - 이미지가 있는 해몽 결과는 이미지와 텍스트가 함께 보여지고, 텍스트만 있는 해몽 결과는 텍스트만 보여짐

9. **회원 로그인 페이지 (/auth)**
   - 구글 및 카카오 소셜 로그인만 존재 
   - 각 소셜 서비스로 성공적으로 로그인 후 리다이렉트는 2번 프로덕트 상세 페이지로 이동

### 5.3 관리자 페이지 구성

0. **관리자 페이지 기본 공통 레이아웃**
   - 좌측 네비게이션 패널 
     * 매출 조회 
     * 주문 내역 리스트 
   - 네비게이션 패널을 제외하고는 각 관리자 메뉴 페이지별 내용 body

1. **관리자 메인 페이지 (/admin)**
   - 기간별 매출 조회 대시보드(기본 화면)

2. **주문 내역 리스트 (/admin/order-list)**
   - 결제가 완료된 주문 건 확인을 위한 리스트 표 
   - 각 리스트 아이템을 누르면 각 주문의 3번 상세 주문 내역으로 이동

3. **상세 주문 내역 (/admin/order-list/[order-id])**
   - 2번에 종속된 페이지 
   - 해당 주문의 회원/비회원 여부, 구매자 정보, 결제 완료 여부, 유저의 꿈 input, LLM이 생성한 해몽 텍스트, AI가 생성한 꿈 이미지(존재한다면), LLM 해몽 재생성 요청 버튼

4. **유저 리스트 (/admin/user-list)**
   - 회원 and 비회원 유저 리스트 표 페이지 
   - 회원과 비회원을 필터링해서 볼 수 있는 기능 
   - 각 회원의 결제 여부를 확인할 수 있음

## 6. API 설계 구조 (백엔드 작업용)
Next.js App Router의 Route Handlers (`app/api/...`) 및 Supabase를 기준으로 MECE(Mutually Exclusive, Collectively Exhaustive)하게 설계된 API 구조입니다. 필요에 따라 데이터 변경(Mutation) 로직은 Next.js Server Actions로 전환하여 구현할 수 있습니다.

### 6.1 인증 및 유저 관리 (Auth & Users)
- **`POST /api/auth/guest/login`**: 비회원 로그인 (전화번호 및 비밀번호 기반 인증 처리)
- **`POST /api/auth/guest/logout`**: 비회원 로그아웃 처리
- **`GET /api/users/me`**: 현재 로그인된 유저(회원/비회원)의 프로필 정보 및 권한 조회
- **`PATCH /api/users/me`**: 회원 프로필 수정 (닉네임 등)
*(※ 회원의 소셜 로그인은 Supabase Auth의 OAuth 기능을 우선 활용합니다.)*

### 6.2 꿈 해몽 및 피드 (Dreams)
- **`GET /api/dreams/feed`**: 공개 설정된 유저들의 해몽 결과 리스트 조회 (피드 페이지용, Pagination 지원)
- **`GET /api/dreams/[dream-id]`**: 특정 해몽 결과 상세 조회 (해석 확인 페이지용)
- **`POST /api/dreams/generate`**: (내부/웹훅) 결제 완료 후 Gemini API를 호출하여 해몽 텍스트 및 이미지를 생성하고 DB에 저장

### 6.3 주문 및 결제 (Orders & Payments)
- **`POST /api/orders`**: 새로운 꿈 해몽 주문 생성 (입력한 꿈 내용, 선택 옵션, 전문 분야 저장 후 임시 `order-id` 발급)
- **`GET /api/orders/me`**: 본인(회원/비회원)의 결제 및 주문 내역 리스트 조회 (마이페이지, 비회원 주문 조회용)
- **`GET /api/orders/[order-id]`**: 특정 주문 및 결제 상세 상태 조회
- **`POST /api/payments/confirm`**: 토스페이먼츠 결제 승인 요청 및 DB 상태 업데이트 (성공 시 `dreams/generate` 로직 비동기 트리거)

### 6.4 관리자 전용 (Admin) - *Admin 권한 검증 필수*
- **`GET /api/admin/dashboard`**: 기간별 전체 매출, 주문 건수 등 통계 데이터 조회
- **`GET /api/admin/orders`**: 전체 주문 내역 리스트 조회 (회원/비회원, 결제 상태 필터 및 Pagination 지원)
- **`GET /api/admin/orders/[order-id]`**: 단일 주문 상세 내역 조회 (유저 원본 입력, LLM 결과, AI 이미지 포함)
- **`POST /api/admin/orders/[order-id]/regenerate`**: 특정 주문의 해몽 텍스트/이미지를 LLM을 통해 강제로 재생성
- **`GET /api/admin/users`**: 가입된 유저 및 결제 이력이 있는 비회원 리스트 조회 (필터링 및 Pagination 지원)

## 7. 데이터베이스 스키마 설계 (DB Schema)
Supabase (PostgreSQL) 환경을 기준으로 MECE하게 설계된 테이블 구조입니다. 각 테이블명과 칼럼명은 직관적으로 구성되었습니다.

### 7.1 `users` 테이블 (회원 및 비회원 프로필)
Supabase Auth(`auth.users`)와 연동되거나 비회원용 자체 인증(전화번호) 정보를 통합 관리하는 테이블입니다.

| Column Name | Data Type | Null 여부 | Description |
| :--- | :--- | :--- | :--- |
| `id` | UUID | Not Null | PK, 회원인 경우 `auth.users.id`와 매핑, 비회원인 경우 UUID 자동 생성 |
| `role` | VARCHAR | Not Null | 유저 권한 (Enum: `admin`, `member`, `guest`) |
| `nickname` | VARCHAR | Null | 회원의 닉네임 |
| `phone_number` | VARCHAR | Null | 비회원 로그인용 전화번호 (회원의 경우 Null) |
| `password_hash` | VARCHAR | Null | 비회원 로그인용 비밀번호 해시 |
| `created_at` | TIMESTAMPTZ | Not Null | 계정 생성 일시 (Default: now()) |
| `updated_at` | TIMESTAMPTZ | Not Null | 계정 수정 일시 (Default: now()) |

### 7.2 `orders` 테이블 (주문 및 결제 정보)
토스페이먼츠 연동을 통한 결제 상태와 금액 내역을 관리하는 테이블입니다.

| Column Name | Data Type | Null 여부 | Description |
| :--- | :--- | :--- | :--- |
| `id` | UUID | Not Null | PK, 주문 고유 ID |
| `user_id` | UUID | Not Null | FK (`users.id`), 주문자 ID (회원 또는 비회원) |
| `status` | VARCHAR | Not Null | 결제 상태 (Enum: `pending`, `paid`, `failed`, `cancelled`) |
| `total_amount` | INTEGER | Not Null | 최종 결제 금액 (예: 텍스트 기본 1500, 이미지 추가 시 2000 등) |
| `payment_key` | VARCHAR | Null | 토스페이먼츠에서 발급받은 결제 키 (승인 시 업데이트) |
| `created_at` | TIMESTAMPTZ | Not Null | 주문 생성 일시 (Default: now()) |
| `updated_at` | TIMESTAMPTZ | Not Null | 주문 업데이트 및 결제 완료 일시 (Default: now()) |

### 7.3 `dreams` 테이블 (꿈 원본 및 AI 해몽 결과)
사용자의 입력과 AI(Gemini API)가 생성한 해몽 텍스트 및 이미지를 저장하는 테이블입니다. `orders` 테이블과 1:1 관계를 가집니다.

| Column Name | Data Type | Null 여부 | Description |
| :--- | :--- | :--- | :--- |
| `id` | UUID | Not Null | PK, 꿈 해몽 고유 ID |
| `order_id` | UUID | Not Null | FK (`orders.id`), 연결된 주문 ID (Unique) |
| `user_id` | UUID | Not Null | FK (`users.id`), 작성자 ID |
| `content` | TEXT | Not Null | 사용자가 입력한 꿈의 원본 내용 |
| `expert_type` | VARCHAR | Not Null | 선택한 해몽 전문 분야 (Enum: `freud`, `jung`, `neuroscience`, `gestalt`) |
| `include_image` | BOOLEAN | Not Null | AI 이미지 생성 옵션 구매 여부 |
| `interpretation_text` | TEXT | Null | AI가 생성한 해몽 텍스트 (AI 처리 완료 전엔 Null) |
| `interpretation_image_url`| VARCHAR | Null | AI가 생성한 해몽 이미지 URL (생성 전이거나 옵션 미구매시 Null) |
| `is_public` | BOOLEAN | Not Null | 피드 공개 여부 (Default: true) |
| `status` | VARCHAR | Not Null | AI 생성 상태 (Enum: `pending`, `generating`, `completed`, `failed`) |
| `created_at` | TIMESTAMPTZ | Not Null | 해몽 요청 생성 일시 (Default: now()) |
| `updated_at` | TIMESTAMPTZ | Not Null | 해몽 완료/수정 일시 (Default: now()) |