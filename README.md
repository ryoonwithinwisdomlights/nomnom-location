# 쩝쩝Location (NomNom Location)

> **Location-Based Restaurant Discovery Platform with Real-time Map Integration**

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://ryoon-with-nomnom-googlemap.vercel.app/)

![logo](https://ryoon-with-nomnom-googlemap.vercel.app/nom_logo.png)

![screenshot](https://ryoon-with-nomnom-googlemap.vercel.app/screenshot.png)

## 📋 About

**쩝쩝Location**은 사용자의 위치를 기반으로 주변 맛집을 실시간으로 발견하고 탐색할 수 있는 위치 기반 서비스 웹 애플리케이션입니다.

Google Maps API와 Google Places API를 활용하여 지도 인터페이스와 장소 정보를 제공하며, NextAuth.js를 통한 Google OAuth 로그인을 지원합니다.

**🔗 Live Demo:** [https://ryoon-with-nomnom-googlemap.vercel.app/](https://ryoon-with-nomnom-googlemap.vercel.app/)

---

## ⚙️ Tech Stack

- **Frontend:** Next.js 14 (App Router), TypeScript, React, Tailwind CSS
- **Maps & Location:** Google Maps JavaScript API, Google Places API
- **Authentication:** NextAuth.js (Google OAuth 2.0)
- **State Management:** React Context API
- **Deployment:** Vercel

---

## ✨ Features

- 🗺️ **Interactive Map** - Google Maps 기반 실시간 지도 인터페이스
- 📍 **Location-Based Search** - 사용자 위치 기반 주변 맛집 검색 (반경 500m~5km)
- 🍽️ **Category Filter** - 마라탕, 족발, 타코, 파스타 등 음식 카테고리별 필터링
- ⭐ **Rating Filter** - 별점 기준 장소 필터링
- 🔐 **Google OAuth** - NextAuth.js 기반 소셜 로그인
- 📱 **Responsive Design** - 모바일/데스크탑 반응형 UI

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- Google Cloud Platform account with:
  - Google Maps JavaScript API enabled
  - Google Places API enabled
  - OAuth 2.0 Client ID/Secret

### Installation

1. Clone the repository
```bash
git clone https://github.com/ryoonwithinwisdomlights/restaurant-rate-app.git
cd restaurant-rate-app
```

2. Install dependencies
```bash
npm install
```

3. Create `.env.local` file in the root directory:

```bash
# Google OAuth (NextAuth.js)
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

# Google Maps & Places API
NEXT_PUBLIC_GOOGLE_API_KEY=your_google_maps_api_key
NEXT_PUBLIC_GOOGLE_MAP_ID=your_google_map_id

# NextAuth Secret (required for production)
SECRET=your_nextauth_secret
```

4. Run the development server
```bash
npm run dev
```

5. Open [http://localhost:3000](http://localhost:3000)

### Environment Variables

Get your credentials from [Google Cloud Console](https://console.cloud.google.com/):
- Enable **Google Maps JavaScript API** and **Google Places API**
- Create **API Key** for Maps/Places APIs
- Create **OAuth 2.0 Client ID** for authentication
- Set authorized redirect URI: `http://localhost:3000/api/auth/callback/google`

For detailed setup guide, see:
- [Google Maps API Documentation](https://developers.google.com/maps/documentation/javascript)
- [NextAuth.js Documentation](https://next-auth.js.org/)

### Deployment

Deploy to Vercel:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/ryoonwithinwisdomlights/restaurant-rate-app)

Remember to add all environment variables in Vercel dashboard.

---

## 📂 Project Structure

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

## 🔜 Future Improvements

- 🔍 Text Search API 통합 (자동완성)
- 🌙 Dark Mode 지원
- 🗺️ Directions API 통합 (경로 안내)
- ⭐ 사용자 리뷰/평점 작성 기능
- 📌 즐겨찾기 기능

---

## 📸 Screenshot

![Desktop Screenshot](https://ryoon-with-nomnom-googlemap.vercel.app/screenshot.png)

---

## 📚 Credits

This project was inspired by [Build Location-Based NextJs13 App](https://youtu.be/SGsDxZukodQ) tutorial and rewritten in TypeScript with additional features.

## 📄 License

MIT License

## 👤 Author

**Seryun Cheon (Ryoon)**  
GitHub: [@ryoonwithinwisdomlights](https://github.com/ryoonwithinwisdomlights)
