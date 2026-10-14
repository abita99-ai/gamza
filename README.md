# 🥔 감자마켓 (Gamza)

> **포근하고 따뜻한 우리 동네 중고거래 웹 서비스**  
> 당근마켓/중고나라 스타일의 미니멀 모던 UI와 Supabase 실시간 데이터베이스 연동을 갖춘 웹 애플리케이션입니다.

---

## 📖 프로젝트 소개

**감자마켓(Gamza)**은 이웃 간의 따뜻한 중고거래를 위해 제작된 반응형 웹 서비스입니다.  
포근한 감자 컬러 테마(`구운 감자 브라운 & 알감자 옐로우`)와 당근 공식 디자인 철학(SEED Design 토큰)을 바탕으로 직관적이고 친근한 사용자 경험을 제공합니다.

---

## ✨ 주요 기능

1. **상품 목록 및 탐색 (`screen1_list.html`, `index.html`)**
   - 모바일 우선 ~ 데스크톱 4열 반응형 그리드 뷰
   - 카테고리별 필터링 (디지털기기, 생활가전, 가구/인테리어, 패션의류 등)
   - 실시간 상품 검색 및 정렬 (최신순, 인기순, 저가순, 고가순)
   - 판매 상태별 뱃지 표시 (`판매중`, `예약중`, `거래 완료`)

2. **상품 상세 정보 모달 (`screen2_detail.html`)**
   - 상품 이미지 갤러리 및 상세 설명
   - 판매자 매너온도 및 프로필 정보
   - 찜하기(관심상품) 및 가격 할인/키워드 알림 신청
   - 거래 상태 변경 시뮬레이션

3. **중고물품 판매 글쓰기 (`screen3_write.html`)**
   - 다중 이미지 업로드 및 미리보기
   - 거래 희망 장소 및 직거래/택배 옵션 선택
   - 가격 제안 받기 옵션 및 유효성 검사

4. **실시간 데이터베이스 연동 (Supabase Backend)**
   - Supabase Database (`products`, `profiles`, `product_likes`, `product_notifications` 테이블 연동)
   - Supabase Realtime 채널을 통한 실시간 피드 업데이트
   - 네트워크 미연결 시 로컬 목데이터(Mock Data) 폴백(Fallback) 지원

---

## 🛠 기술 스택

- **Frontend**: Vanilla HTML5, CSS3, Modern JavaScript (ES6+)
- **Typography**: Pretendard Web Font
- **Backend / DB**: [Supabase](https://supabase.com/) (PostgreSQL & Realtime Client)
- **Deployment**: GitHub Pages / Static Web Hosting

---

## 📁 디렉터리 및 파일 구조

```
Gamza/
├── index.html              # 통합 메인 애플리케이션 (목록 + 상세 + 글쓰기 통합 SPA)
├── screen1_list.html       # 상품 피드 및 목록 화면
├── screen2_detail.html     # 상품 상세 정보 모달 화면
├── screen3_write.html      # 상품 등록 및 글쓰기 화면
├── design_system.md        # 감자마켓 브랜드 디자인 시스템 가이드
├── .env.example            # 환경변수 설정 가이드 (민감정보 제외 템플릿)
├── .gitignore              # Git 제외 파일 목록 (비밀키 및 임시 파일 보호)
└── README.md               # 프로젝트 안내 문서
```

---

## 🚀 시작하기

### 로컬에서 실행하기

이 프로젝트는 별도의 빌드 단계가 필요 없는 순수 정적 웹 애플리케이션입니다.

1. **저장소 클론**
   ```bash
   git clone https://github.com/abita99-ai/gamza.git
   cd gamza
   ```

2. **브라우저에서 실행**
   - VS Code의 **Live Server** 확장을 사용하여 `index.html`을 실행하거나,
   - `index.html` 파일을 더블 클릭하여 브라우저에서 바로 열 수 있습니다.

### Supabase 환경 설정

- Supabase 프로젝트 연동 시 `.env.example` 파일을 참고하여 프로젝트 URL 및 공개 Anon Key를 확인하세요.
- 기본 브라우저 연동 키(`SUPABASE_URL`, `SUPABASE_ANON_KEY`)는 클라이언트 공개용 키이며, 백엔드 관리자 키(`service_role`)는 절대 프론트엔드나 원격 저장소에 노출되지 않도록 주의해야 합니다.

---

## 🌐 GitHub Pages 배포 안내

이 저장소는 루트 경로에 `index.html`이 배치되어 있어 GitHub Pages로 간편하게 무료 호스팅할 수 있습니다.

1. GitHub 저장소 상단 탭에서 **Settings** 클릭
2. 좌측 메뉴에서 **Pages** 선택
3. **Build and deployment** > **Source** 항목에서 `Deploy from a branch` 선택
4. **Branch**를 `main` 브랜치 / `/ (root)` 로 지정 후 **Save** 클릭
5. 몇 분 후 제공되는 URL (`https://<username>.github.io/gamza/`)로 접속 가능합니다.

---

## 📄 라이선스

이 프로젝트는 학습 및 실습 목적으로 제작되었습니다.
