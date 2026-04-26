# 맛집 큐레이션 리스트

Notion을 CMS로 활용한 개인 맛집 기록 및 공유 웹서비스입니다.

## 프로젝트 개요

Notion 데이터베이스에 식당 정보를 입력하면 Next.js 웹사이트에 자동으로 반영됩니다. 비개발자도 Notion에서 직접 콘텐츠를 관리할 수 있습니다.

## 주요 기능

- **맛집 목록 조회** — Notion DB 연동, 카드형 UI
- **카테고리 / 별점 필터링** — 한식·중식·양식 등 실시간 필터
- **맛집 상세 페이지** — 식당 정보, 한줄평, 카카오맵 링크

## 기술 스택

| 레이어 | 기술 |
|--------|------|
| Frontend | Next.js 15, TypeScript |
| CMS | Notion API |
| Styling | Tailwind CSS, shadcn/ui |
| Icons | Lucide React |
| 배포 | Vercel |

## 시작하기

### 1. 저장소 클론

```bash
git clone https://github.com/<your-username>/my-starter-kit.git
cd my-starter-kit
```

### 2. 의존성 설치

```bash
npm install
```

### 3. 환경변수 설정

`.env.local` 파일을 생성하고 아래 값을 입력합니다.

```env
NOTION_API_KEY=secret_xxxxxxxxxxxxxxxxxxxx
NOTION_DATABASE_ID=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
NEXT_PUBLIC_SITE_URL=http://localhost:3000
```

### 4. 개발 서버 실행

```bash
npm run dev
```

브라우저에서 [http://localhost:3000](http://localhost:3000) 을 열어 확인합니다.

## Notion 데이터베이스 구조

| 필드명 | 타입 | 설명 |
|--------|------|------|
| 식당명 | Title | 식당 이름 (필수) |
| 카테고리 | Select | 한식 / 중식 / 양식 / 일식 / 기타 |
| 별점 | Number | 1 ~ 5점 |
| 위치 | Rich Text | 주소 또는 지역명 |
| 카카오맵 URL | URL | 카카오맵 바로가기 링크 |
| 방문일 | Date | 최근 방문 날짜 |
| 한줄평 | Rich Text | 짧은 리뷰 (100자 이내 권장) |
| 썸네일 | Files & Media | 음식 또는 외관 사진 |
| 공개 여부 | Checkbox | 웹에 노출할지 여부 |

## 문서

- [PRD (제품 요구사항 정의서)](./docs/PRD.md)

## 라이선스

MIT
