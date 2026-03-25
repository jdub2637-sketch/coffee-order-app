# Coffee Order & Aggregation Web App Specification

## 1. Project Overview
- **Goal**: 식사 후 교사들의 커피 주문을 효율적으로 수집하고 집계하는 웹 애플리케이션.
- **Target Users**: 선생님(주문자), 관리자(메뉴 및 가격 설정자).
- **Key Value**: 별도의 백엔드 서버 없이 구글 스프레드시트를 활용한 실시간 데이터 관리.

## 2. Target Features

### A. Admin (관리자)
- **메뉴 등록**: 오늘의 커피 메뉴 이름 입력.
- **가격 설정**: 각 메뉴에 해당하는 가격 입력.
- **설정 저장**: 입력된 메뉴와 가격을 로컬 상태 또는 로컬 스토리지에 저장 (세션 유지).

### B. User (사용자)
- **주문자 식별**: 본인의 '이름' 입력 (필수).
- **메뉴 선택**: 관리자가 등록한 메뉴 중 하나를 선택.
- **주문하기**: 버튼 클릭 시 데이터 전송.

### C. Data Integration
- **Webhook 전송**: Fetch API를 사용하여 구글 스프레드시트로 데이터 전송.
  - 전송 데이터: `{ "name": "이름", "menu": "메뉴명", "price": 가격, "timestamp": "시간" }`
- **응답 처리**: 주문 완료 후 성공 메시지 표시.

## 3. Tech Stack
- **Frontend**: React + Vite
- **Styling**: Vanilla CSS (Glassmorphism 적용)
- **Deployment**: (추후 결정)
- **Backend**: Google Apps Script (Web App URL)

## 4. Design Guide (Glassmorphism)
- **Background**: 은은한 커피/카페 분위기의 이미지 (Blur 처리).
- **UI Components**:
  - 반투명 흰색 배경 (`rgba(255, 255, 255, 0.2)` 등).
  - 부드러운 테두리 (`border-radius: 15px`).
  - 블러 효과 (`backdrop-filter: blur(10px)`).
  - 현대적이고 깔끔한 폰트 사용.
- **Responsiveness**: 모바일 환경 최적화 (Mobile-first).

## 5. Configuration
- **Webhook URL**: `const WEBHOOK_URL = "YOUR_GOOGLE_APPS_SCRIPT_URL_HERE";` (가상의 변수로 분리)
