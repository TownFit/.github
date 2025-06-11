<p align="center">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/House.png" alt="House" width="120" height="120" />
</p>

<h1 align="center">동네 Fit (Town Fit)</h1>

<p align="center">
  <strong>"나에게 딱 맞는 스마트한 동네, AI가 10초 만에 찾아드려요."</strong>
  <br />
  개인별 라이프스타일에 최적화된 맞춤형 동네 추천 서비스
</p>

<p align="center">
  <a href="#-시작하기"><strong>🚀 서비스 바로가기</strong></a> •
  <a href="#-주요-기능"><strong>✨ 주요 기능</strong></a> •
  <a href="#-시스템-아키텍처"><strong>🏛️ 아키텍처</strong></a> •
  <a href="#-기술-스택"><strong>🛠️ 기술 스택</strong></a> •
  <a href="#-만든-사람들"><strong>👨‍💻 팀 소개</strong></a>
</p>

---

### 🤔 **이런 고민, 해본 적 없으신가요? (The Problem)**

> "중학생 자녀가 있고, 나이 많은 반려견도 있는데… 어디로 이사 가야 할까?" <br>
> "인프라가 잘 갖춰진 동네를 찾고 싶은데, 정보를 일일이 검색하기 너무 힘들어."

우리는 모두 각자의 생활 방식에 맞는 최적의 주거 환경을 꿈꿉니다. 하지만 동네의 수많은 인프라 정보를 직접 비교하고, 나의 조건에 맞는 곳을 찾는 것은 시간과 노력이 많이 드는 일입니다.

### 💡 **`동네 Fit`이 이렇게 해결해 드립니다! (The Solution)**
![Introduction](https://github.com/TownFit/.github/blob/main/images/before_after.png?raw=true)
`동네 Fit`은 복잡한 정보 검색 과정을 없애고, **단 10초** 만에 당신에게 가장 적합한 동네를 찾아주는 스마트한 솔루션입니다.

-   **간단한 설문:** 몇 가지 질문에 답하는 것만으로 추천 준비 끝!
-   **AI 기반 추천:** Gemini AI가 수만 개의 시설 데이터를 분석하여 최적의 동네를 추천합니다.
-   **직관적인 결과:** 왜 이곳이 추천되었는지, 어떤 시설이 있는지 지도를 통해 한눈에 확인하세요.

---

## 🚀 시작하기 (Live Demo)

> 지금 바로 나에게 딱 맞는 동네를 찾아보세요!

<p align="center">
  <a href="https://frontend-omega-opal-86.vercel.app/" target="_blank">
    <img src="https://github.com/TownFit/TownFit/blob/main/images/preview.png?raw=true" alt="동네 Fit 서비스 메인 화면" width="800px"/>
  </a>
  <br/>
  <a href="https://frontend-omega-opal-86.vercel.app/" target="_blank">
    <img src="https://vercel.com/button" alt="Deploy with Vercel"/>
  </a>
</p>

---

## ✨ 주요 기능 (How It Works)

`동네 Fit`은 4단계의 체계적인 흐름을 통해 사용자에게 최고의 경험을 제공합니다.

| 단계 | 기능 | 상세 설명 |
| :--: | :-- | :--- |
| **1️⃣** | **설문 조사** | 자녀, 반려동물, 선호 시설 등 간단한 설문을 통해 사용자의 라이프스타일 정보를 수집합니다. |
| **2️⃣** | **LLM 분석** | **Gemini AI**가 사용자 정보를 바탕으로 DB에 저장된 1만 개 이상의 인프라 중 가장 적합한 시설들을 분석하고 추천합니다. |
| **3️⃣** | **동네 추천** | 추천된 시설들을 **DBSCAN 기반 커스텀 클러스터링 알고리즘**으로 분석하여, 최적의 동네(권역)를 지도 위에 시각적으로 제안합니다. |
| **4️⃣** | **상세 설명** | 각 추천 동네의 순위, 편의도 점수와 함께 AI가 분석한 구체적인 추천 이유, 관련 부동산 정보까지 한눈에 제공합니다. |

---

## 🏛️ 시스템 아키텍처 (System Architecture)

![System Architecture](https://github.com/TownFit/.github/blob/main/images/architecture.png?raw=true)

1.  **Frontend (React & Vercel)**
    -   사용자는 Vercel에 배포된 **React** 앱을 통해 서비스를 이용합니다.
    -   **Google OAuth**로 안전하게 사용자를 인증하고, **Naver Map API**를 통해 지도를 시각화합니다.

2.  **Backend (FastAPI & AWS)**
    -   API 요청은 **Route53**과 **Load Balancer**를 거쳐 **AWS EC2**에서 실행되는 **FastAPI** 서버로 라우팅됩니다.
    -   서버는 프론트에서 받은 인증 토큰을 Google에 직접 검증하여 보안을 강화합니다.
    -   핵심 로직은 **Gemini API**를 호출하여 사용자 맞춤형 추천 결과를 생성합니다.

3.  **Database (PostgreSQL)**
    -   사용자 정보, 시설 데이터, 추천 기록 등 모든 데이터는 **PostgreSQL** DB에 체계적으로 저장 및 관리됩니다.

4.  **CI/CD (Docker & GitHub Actions)**
    -   **GitHub Actions**를 통해 코드 변경 시 **Docker** 이미지를 자동으로 빌드하여 지속적 통합(CI) 파이프라인을 구축했습니다.

## 🛠️ 기술 스택 (Tech Stack)

| 구분 | 기술 |
| :--- | :--- |
| **Frontend** | <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black"> <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"> |
| **Backend** | <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white"> <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"> |
| **Database** | <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"> |
| **Infrastructure** | <img src="https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white"> <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white"> <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> |
| **LLM & API** | <img src="https://img.shields.io/badge/Gemini-8E75CE?style=for-the-badge&logo=google-gemini&logoColor=white"> `Naver Map API` |
| **DevOps** | <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white"> |

## 🗄️ 데이터베이스 스키마 (Database Schema)

![Database Schema](https://github.com/TownFit/.github/blob/main/images/erd.png?raw=true)

-   **`users`**: 가입한 사용자 정보를 저장합니다.
-   **`facility_types`**: '동물병원', '중학교' 등 인프라의 종류와 설명을 정의합니다.
-   **`facilities`**: 공공 데이터를 기반으로 수집된 각 시설의 이름, 위치(좌표) 등의 정보를 저장합니다.
-   **`recommendations`**: 특정 사용자에게 어떤 시설 타입이 추천되었는지 기록하여 AI 분석에 활용합니다.

## 📂 코드 저장소 (Repositories)

> 프로젝트의 소스 코드가 궁금하신가요?

-   **Frontend:** [github.com/TownFit/frontend](https://github.com/TownFit/frontend)
-   **Backend:** [github.com/TownFit/backend](https://github.com/TownFit/backend)

## 👨‍💻 만든 사람들 (Meet the Team)

> 안녕하세요! 버그 없는 세상을 꿈꾸는 **노모어버그 (No More Bug)** 팀입니다.

| 이름 | 역할 | GitHub |
| :--- | :--- | :--- |
| **전민규** | **Backend & System Lead** <br/> (백엔드, DB, 클러스터링 엔진, 시스템 아키텍처 총괄) | [@Mango-Juice](https://github.com/Mango-Juice) |
| **최평화** | **Frontend & UI/UX Lead** <br/> (프론트엔드, API 연동, 사용자 중심 인터페이스 개발) | [@c-peace](https://github.com/c-peace) |

---
