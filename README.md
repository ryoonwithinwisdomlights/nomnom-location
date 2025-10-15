# 쩝쩝Location (NomNom Location)

> **Location-Based Restaurant Discovery Platform with Real-time Map Integration**

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://ryoon-with-nomnom-googlemap.vercel.app/)
[![Next.js](https://img.shields.io/badge/Next.js-14-black)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)](https://www.typescriptlang.org/)

![logo](https://ryoon-with-nomnom-googlemap.vercel.app/nom_logo.png)

![screenshot](https://ryoon-with-nomnom-googlemap.vercel.app/screenshot.png)

---

## 📋 프로젝트 개요

| 항목        | 내용                                                                                      |
| --------- | --------------------------------------------------------------------------------------- |
| **개발 기간** | 3일 (집중 개발)                                                                              |
| **개발 범위** | 기획 · 설계 · 개발 · 배포 전 과정 100% 단독 수행                                                      |
| **배포 환경** | [Vercel](https://vercel.com)                                                            |
| **레퍼런스**  | [Build Location-Based NextJs13 App](https://youtu.be/SGsDxZukodQ) (JS → TS로 재작성)     |
| **데모 링크** | [ryoon-with-nomnom-googlemap.vercel.app](https://ryoon-with-nomnom-googlemap.vercel.app) |

**쩝쩝Location**은 사용자의 위치를 기반으로 주변 맛집을 실시간으로 발견하고 탐색할 수 있는 위치 기반 서비스(LBS) 웹 애플리케이션입니다.  
Google Maps API와 Google Places API를 활용하여 직관적인 지도 인터페이스와 상세한 장소 정보를 제공하며,  
NextAuth.js를 통한 Google 소셜 로그인 기능을 구현했습니다.

---

## ⚙️ 기술 스택

| 영역                     | 기술                                                                       |
| ---------------------- | ------------------------------------------------------------------------ |
| **Frontend**           | Next.js 14 (App Router), TypeScript, React, Tailwind CSS             |
| **Maps & Location**    | Google Maps JavaScript API, Google Places API (Nearby Search)           |
| **Authentication**     | NextAuth.js (Google OAuth 2.0)                                           |
| **State Management**   | React Context API (UserLocationContext, SelectedBusinessContext)         |
| **Custom Hooks**       | useGeolocation (Geolocation API)                                         |
| **UI/UX**              | Radix UI (Dropdown), Custom Skeleton Loading, Responsive Design          |
| **API Architecture**   | Next.js API Routes (`/api/google-place`, `/api/auth/[...nextauth]`)  |
| **Infra / Deploy**     | Vercel, Environment Variables Configuration                      |
| **Type Safety**        | TypeScript Interfaces (`interface/response.ts`), Strict Type Definitions |

---

## 🧩 주요 기능 (Key Features)

### 🗺️ **Interactive Map Experience**
- **Google Maps 실시간 통합** — 사용자 위치 기반 동적 지도 렌더링
- **Custom Markers** — 선택된 비즈니스의 시각적 강조 표시
- **반응형 지도 인터페이스** — 모바일부터 데스크탑까지 최적화된 뷰포트

### 📍 **Location-Based Search**
- **Geolocation API 활용** — 사용자의 현재 위치 자동 감지
- **Nearby Search (Places API)** — 주변 맛집 실시간 검색
- **반경 필터링** — 500m ~ 5km 범위 내 거리 기반 검색
- **평점 필터** — 별점 기준으로 고품질 장소 필터링

### 🍽️ **Category-Based Discovery**
- **커스텀 카테고리 시스템** — 마라탕, 족발, 타코, 파스타 등 큐레이션된 음식 카테고리
- **아이콘 기반 UI** — 직관적인 카테고리 선택 인터페이스
- **동적 카테고리 검색** — 선택한 카테고리에 따른 실시간 장소 업데이트

### 🔐 **Authentication**
- **Google OAuth 2.0** — NextAuth.js 기반 소셜 로그인
- **세션 관리** — 서버 사이드 세션 처리

### 📱 **Business Information**
- **상세 정보 표시** — 이름, 주소, 평점, 영업 상태, 리뷰 수
- **장소 사진** — Google Places의 장소 사진 표시
- **Google Maps 연동** — 장소 클릭 시 Google Maps로 바로 이동

### 🎨 **User Experience**
- **Skeleton Loading** — 데이터 로딩 중 시각적 피드백
- **Responsive Design** — 완전한 반응형 레이아웃
- **에러 핸들링** — Geolocation 권한 거부, API 에러 등 엣지 케이스 처리

---

## 💡 기술적 인사이트 및 주요 구현 사항
**Google Maps API와 Next.js App Router를 활용한 위치 기반 서비스 구현**

| 역량 영역                              | 설명                                                                                                                                                    |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Full Ownership**                 | 기획 → 설계 → 개발 → 배포 전 과정을 단독 수행. JavaScript 레퍼런스를 TypeScript로 재작성.                                        |
| **Location-Based Service (LBS)**   | Geolocation API, Google Maps JavaScript API, Google Places API를 통합한 위치 기반 서비스 구현. 브라우저 권한 처리, 위치 업데이트 등 구현. |
| **API Integration** | Next.js API Routes로 서버 사이드 API 프록시 구현. Google Places API 호출을 백엔드에서 처리하여 API 키 보안 강화.                                                 |
| **Type-Safe Development**          | TypeScript 기반 코드베이스 구성. `interface/response.ts`에서 Google Places API 응답 타입 정의.                                                |
| **State Management**       | Context API로 전역 상태 관리 (`UserLocationContext`, `SelectedBusinessContext`).                                       |
| **Custom Hooks**       | `useGeolocation` 훅을 구현하여 Geolocation API를 React 생명주기와 통합. 권한 요청, 에러 처리 등 구현.                                           |
| **Component Architecture**         | `CategoryList`, `BusinessList`, `BusinessItem`, `Markers` 등으로 컴포넌트 분리.                                     |
| **UX**       | Skeleton Loading으로 로딩 상태 시각화.                                                                    |
| **Authentication**            | NextAuth.js의 OAuth 플로우 이해. Google Provider 설정 및 세션 처리 구현.                                                            |
| **Environment Setup**           | Vercel 배포 환경에서 환경 변수 관리. 로컬/프로덕션 환경 분리.                                          |
| **TypeScript Migration**                | JavaScript 레퍼런스를 TypeScript로 재작성. 타입 정의 및 에러 핸들링 추가.                              |

> 🎯 **한 줄 요약:**  
> "JavaScript 레퍼런스를 TypeScript로 재작성하며 Google Maps API와 위치 기반 서비스를 학습한 프로젝트입니다."

---

## 🧠 제작 과정 및 학습 포인트

이 프로젝트는 **Mapping 라이브러리 경험 확보**를 목표로 시작하여, Google Maps API와 위치 기반 서비스의 기본 구조를 학습할 수 있었습니다.

### 🔄 TypeScript Migration
- 원본 강의는 JavaScript 기반이었으나, 타입 안정성을 위해 TypeScript로 재작성.
- Google Maps API와 Google Places API의 응답 구조에 맞춰 인터페이스 정의.
- NextAuth.js의 타입 정의 학습.

### 🗺️ Google Maps API
- Google Maps JavaScript API의 `Map`, `Marker` 클래스 활용.
- Google Places API의 Nearby Search를 통해 `location`, `radius`, `type`, `keyword` 파라미터 활용.
- API 키 관리 및 기본적인 에러 핸들링 구현.

### 🎯 Location-Based Service
- Geolocation API의 `getCurrentPosition`을 활용한 현재 위치 감지.
- 위치 권한 요청 플로우 구현.

### 🔐 OAuth 2.0
- NextAuth.js를 통한 Google OAuth 2.0 구현.
- Google Cloud Console에서 OAuth 2.0 클라이언트 설정.

### 🚀 Next.js App Router
- `app/` 디렉토리 구조에서 Server Component, Client Component 구분.
- API Routes (`app/api/`)로 서버 사이드 API 프록시 구현하여 API 키 보안.

---

## 🚀 실행 및 환경 구성

### Prerequisites
- Node.js 18+ 
- Google Cloud Platform 계정 (Maps API, Places API 활성화 필요)
- Google OAuth 2.0 클라이언트 ID/Secret

### 환경 변수 설정

프로젝트 루트에 `.env.local` 파일을 생성하고 아래 변수를 설정하세요:

```bash
# Google OAuth (NextAuth.js)
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

# Google Maps & Places API
NEXT_PUBLIC_GOOGLE_API_KEY=your_google_maps_api_key
NEXT_PUBLIC_GOOGLE_MAP_ID=your_google_map_id

# NextAuth Secret (Production)
# 로컬 개발 시에는 자동 생성되지만, 프로덕션 배포 시 필수
SECRET=your_nextauth_secret
```

### 환경 변수 상세 설명

| 변수                                | 설명                                                                                                                               |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `GOOGLE_CLIENT_ID`                | Google Cloud Console에서 발급받은 OAuth 2.0 클라이언트 ID.  [Google Cloud Console - Credentials](https://console.cloud.google.com/apis/credentials) |
| `GOOGLE_CLIENT_SECRET`            | OAuth 2.0 클라이언트 시크릿 키.                                                                                                           |
| `NEXT_PUBLIC_GOOGLE_API_KEY`      | Google Maps JavaScript API 및 Places API 사용을 위한 API 키.                                                                            |
| `NEXT_PUBLIC_GOOGLE_MAP_ID`       | Google Cloud Console에서 생성한 Map ID. (고급 마커 스타일링 등에 사용)                                                                             |
| `SECRET`                          | NextAuth.js 세션 암호화를 위한 시크릿. 프로덕션 배포 시 필수. [생성 방법 참고](https://medium.com/@prodmxle/setting-up-nextauth-js-application-and-deploying-it-via-vercel-d6b02bf98397) |

![환경 변수 예시 1](/public/env1.png)
![환경 변수 예시 2](/public/env2.png)

### Google Cloud Platform 설정

1. **Maps & Places API 활성화**
   - [Google Cloud Console](https://console.cloud.google.com/)에서 프로젝트 생성
   - "APIs & Services" → "Enable APIs and Services"에서 다음 API 활성화:
     - Maps JavaScript API
     - Places API
     - Geocoding API (선택사항)

2. **API 키 생성 및 제한**
   - "Credentials" → "Create Credentials" → "API Key"
   - API 키 제한 설정 (보안 강화):
     - Application restrictions: HTTP referrers (웹사이트)
     - API restrictions: Maps JavaScript API, Places API만 허용

3. **OAuth 2.0 클라이언트 생성**
   - "Credentials" → "Create Credentials" → "OAuth client ID"
   - Application type: Web application
   - Authorized redirect URIs: 
     - `http://localhost:3000/api/auth/callback/google` (개발)
     - `https://your-domain.vercel.app/api/auth/callback/google` (프로덕션)

### 로컬 개발 실행

```bash
# 의존성 설치
npm install

# 개발 서버 실행
npm run dev
```

브라우저에서 [http://localhost:3000](http://localhost:3000) 접속

### 프로덕션 배포 (Vercel)

```bash
# Vercel CLI 설치 (선택사항)
npm i -g vercel

# Vercel에 배포
vercel

# 프로덕션 배포
vercel --prod
```

**Vercel Dashboard에서 환경 변수 설정:**
- Project Settings → Environment Variables에서 위의 모든 환경 변수 추가
- `SECRET` 변수는 프로덕션 환경에 필수로 설정 ([생성 방법](https://medium.com/@prodmxle/setting-up-nextauth-js-application-and-deploying-it-via-vercel-d6b02bf98397))

---

## 📂 프로젝트 구조

```
restaurant-rate-app/
├── app/
│   ├── api/
│   │   ├── auth/[...nextauth]/route.ts    # NextAuth.js 설정
│   │   └── google-place/route.ts          # Google Places API 프록시
│   ├── components/
│   │   ├── HeaderNavbar.tsx               # 네비게이션 바 & 인증 UI
│   │   ├── Home/
│   │   │   ├── BusinessItem.tsx           # 개별 비즈니스 카드
│   │   │   ├── BusinessList.tsx           # 비즈니스 목록 컨테이너
│   │   │   ├── CategoryList.tsx           # 카테고리 선택 UI
│   │   │   ├── GoogleMapView.tsx          # 지도 통합 컴포넌트
│   │   │   ├── Markers.tsx                # 지도 마커 관리
│   │   │   ├── RangeSelect.tsx            # 반경 필터
│   │   │   └── SelectRating.tsx           # 평점 필터
│   │   └── SkeltonLoading.tsx             # 로딩 스켈레톤
│   ├── login/page.tsx                     # 로그인 페이지
│   ├── about/page.tsx                     # About 페이지
│   ├── page.tsx                           # 메인 페이지
│   ├── layout.tsx                         # 루트 레이아웃
│   └── globals.css                        # 글로벌 스타일
├── context/
│   ├── SelectedBusinessContext.ts         # 선택된 비즈니스 상태
│   └── UserLocationContext.ts             # 사용자 위치 상태
├── hooks/
│   └── use-geolocation.tsx                # Geolocation 커스텀 훅
├── interface/
│   └── response.ts                        # API 응답 타입 정의
├── SharedData/
│   ├── Data.ts                            # 카테고리 데이터
│   └── GlobalApi.ts                       # API 호출 유틸리티
└── components/ui/
    └── dropdown-menu.tsx                  # Radix UI 컴포넌트
```

---

## 🔜 향후 개선 하면 좋은 부분

### 🔍 **Search Functionality**
현재 Search 컴포넌트의 구조만 구현되어 있으며, 실제 검색 기능은 추가 예정입니다.
- **Google Places Text Search API** 통합 ([공식 문서](https://developers.google.com/maps/documentation/places/web-service/text-search?hl=ko))
- 자동완성(Autocomplete) 기능 추가
- 검색 히스토리 저장

### 🎨 **UI/UX Enhancement**
- Dark Mode 지원
- 장소 상세 페이지 (리뷰, 사진 갤러리, 영업시간 등)
- 즐겨찾기(Bookmark) 기능

### 🗺️ **Map Features**
- Directions API 통합 (경로 안내)
- 여러 장소 비교 모드
- 클러스터링(많은 마커 처리)

### 📊 **Data & Analytics**
- 사용자 리뷰/평점 작성 기능
- 방문 기록 저장
- 추천 알고리즘 (ML 기반)

---

## 📸 스크린샷

### Desktop View
![Desktop Screenshot](https://ryoon-with-nomnom-googlemap.vercel.app/screenshot.png)

### Key Features
- 실시간 지도 인터랙션
- 카테고리 기반 필터링
- 상세 비즈니스 정보
- Google OAuth 로그인

---

## 🔗 참고 링크

- **Live Demo:** [https://ryoon-with-nomnom-googlemap.vercel.app/](https://ryoon-with-nomnom-googlemap.vercel.app/)
- **Reference Tutorial:** [Build Location-Based NextJs13 App](https://youtu.be/SGsDxZukodQ)
- **Google Maps JavaScript API:** [Documentation](https://developers.google.com/maps/documentation/javascript)
- **Google Places API:** [Documentation](https://developers.google.com/maps/documentation/places/web-service)
- **NextAuth.js:** [Documentation](https://next-auth.js.org/)
- **NextAuth.js Vercel Deployment Guide:** [Medium Article](https://medium.com/@prodmxle/setting-up-nextauth-js-application-and-deploying-it-via-vercel-d6b02bf98397)

---

## 📄 License

This project is open source and available under the MIT License.

---

## 👨‍💻 Author

**Seryun Cheon (Ryoon)**
- GitHub: [@ryoonwithinwisdomlights](https://github.com/ryoonwithinwisdomlights)
