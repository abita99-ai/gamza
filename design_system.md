# 🥔 감자 (Gamza) 중고 거래 웹 서비스 디자인 시스템 & 공통 가이드

## 1. 브랜드 컨셉
- 포근하고 따뜻한 감자 느낌의 라이트 브라운 & 베이지 톤
- 깔끔하고 직관적인 당근마켓/중고나라 스타일의 미니멀 모던 UI
- 반응형 웹 (모바일 우선 ~ 데스크톱 4열 그리드 지원)

## 2. 컬러 팔레트 (CSS Variables)
```css
:root {
  --primary-color: #8D5B4C;        /* 구운 감자 메인 브라운 */
  --primary-hover: #734537;        /* 호버 시 진한 브라운 */
  --primary-light: #F3EAE3;        /* 연한 감자 크림 */
  --accent-gold: #E5A93C;          /* 알감자 옐로우 포인트 */
  --accent-gold-hover: #CF9227;

  --bg-main: #FDFBF8;              /* 전체 배경 밝은 크림베이지 */
  --bg-surface: #FFFFFF;           /* 카드 및 모달 배경 흰색 */
  --bg-input: #F7F5F2;             /* 인풋 배경 */

  --text-main: #2C2523;            /* 메인 텍스트 진한 흑갈색 */
  --text-sub: #7A706A;             /* 서브 텍스트 그레이 */
  --text-muted: #A39B94;           /* 날짜/힌트 텍스트 */
  --border-color: #EFE9E2;         /* 테두리선 */
  --border-focus: #8D5B4C;

  /* 판매 상태 색상 (요구사항 필수) */
  --status-sale-bg: #EAF7EE;       /* 판매중 연한 초록 */
  --status-sale-text: #1B7C3E;
  --status-reserved-bg: #FFF3E0;   /* 예약중 연한 오렌지 */
  --status-reserved-text: #E65100;
  --status-done-bg: #F0F0F0;       /* 거래 완료 연한 회색 */
  --status-done-text: #757575;

  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 18px;
  --radius-full: 9999px;

  --shadow-sm: 0 2px 8px rgba(115, 69, 55, 0.06);
  --shadow-md: 0 6px 20px rgba(115, 69, 55, 0.08);
  --shadow-lg: 0 12px 36px rgba(115, 69, 55, 0.16);
}
```

## 3. 공통 컴포넌트 규격
- **버튼**:
  - 기본: 높이 42px, radius: 10px, font-weight: 600, transition: all 0.2s ease
  - `.btn-primary`: 배경 `--primary-color`, 글자 흰색
  - `.btn-outline`: 테두리 `1px solid var(--border-color)`, 글자 `--text-main`
  - `.btn-gold`: 배경 `--accent-gold`, 글자 흰색
- **상태 뱃지 (`.status-badge`)**:
  - `padding: 4px 10px`, `border-radius: 6px`, `font-size: 12px`, `font-weight: 700`
  - `.status-sale`: 판매중
  - `.status-reserved`: 예약중
- **카테고리 분류**:
  - `전체`, `디지털기기`, `가구/인테리어`, `의류`, `생활가전`, `도서/티켓`, `반려동물 용품`, `실험실과학도구`, `기타`

## 4. 데이터 스키마 (Product Item)
```javascript
{
  id: 1,
  title: "아이패드 에어 5세대 M1 64GB 스페이스그레이 풀박스",
  category: "디지털기기", // "디지털기기" | "가구/인테리어" | "의류" | "생활가전" | "도서/티켓" | "반려동물 용품" | "실험실과학도구" | "기타"
  price: 540000,
  location: "역삼1동",
  uploadedAt: "10분 전",
  status: "판매중", // "판매중" | "예약중" | "거래 완료"
  image: "https://images.unsplash.com/photo-1544244015-0df4b3ffc6b0?w=800&auto=format&fit=crop&q=60",
  description: "실사용 6개월 미만 배터리 효율 98%입니다. 케이스와 액정보호필름 항상 부착하여 기스 전혀 없습니다. 직거래 역삼역 3번출구 희망합니다.",
  seller: {
    nickname: "감자튀김조아",
    profileImg: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=200&auto=format&fit=crop&q=60",
    location: "역삼1동",
    temperature: "37.8°C"
  }
}
```
