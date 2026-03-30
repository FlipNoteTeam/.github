<!-- 서비스 로고/배너 이미지가 있다면 아래에 추가하세요 -->
<!-- <img src="" alt="FlipNote 로고" width="200"/> -->

# 📒 FlipNote (플립노트)

**팀과 함께 만들고, 함께 학습하는 실시간 플래시카드 협업 서비스**

> CRDT 기반 동시 편집 · 그룹 권한 관리 · 스마트 학습 모드

<br/>

[![프론트엔드](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react&logoColor=white)](https://github.com)
[![배포](https://img.shields.io/badge/Deploy-CloudFront%20%2B%20S3-FF9900?logo=amazonaws&logoColor=white)](https://github.com)
[![라이선스](https://img.shields.io/badge/License-MIT-green)](LICENSE)

</div>

---

## 📑 목차

- [서비스 소개](#-서비스-소개)
- [주요 기능](#-주요-기능)
- [아키텍처](#-아키텍처)
- [기술 스택](#-기술-스택)
- [팀원](#-팀원)

---

## 서비스 소개

FlipNote는 **혼자가 아닌 팀과 함께** 플래시카드를 제작하고 학습하는 협업 서비스입니다.

CRDT(Conflict-free Replicated Data Type) 기술을 적용해 여러 사람이 동시에 카드를 편집해도 충돌 없이 실시간 동기화되며, 세분화된 권한 체계(RBAC)로 안전한 팀 협업 환경을 제공합니다. 암기 모드·시험 모드 등 다양한 학습 도구를 통해 학습 효과를 극대화할 수 있습니다.

---

## 주요 기능

### 실시간 협업 편집

**CRDT 기반 동시 편집 지원**

- ✏️ **실시간 동기화**: 여러 사용자가 동시에 카드 편집
- 👀 **편집 내용 즉시 반영**: 다른 사용자의 변경사항 실시간 확인
- 💾 **자동 저장**: 편집 내용 자동 저장으로 데이터 손실 방지
- 🔔 **충돌 방지**: 동시 편집 시 변경사항 병합 처리

| 실시간 편집 화면 1 | 실시간 편집 화면 2 |
|:---:|:---:|
| ![실시간편집1](./images/realtime-edit-1.png) | ![실시간편집2](./images/realtime-edit-2.png) |

| 실시간 편집 화면 3 | 실시간 편집 화면 4 |
|:---:|:---:|
| ![실시간편집3](./images/realtime-edit-3.png) | ![실시간편집4](./images/realtime-edit-4.png) |

---

### 카드셋 즐겨찾기 & 좋아요

**내 관심 카드셋 한눈에 관리**

- ⭐ **즐겨찾기**: 자주 쓰는 카드셋을 즐겨찾기로 빠르게 접근
- ❤️ **좋아요**: 유용한 카드셋에 좋아요 표시 및 좋아요순 정렬 지원

| 즐겨찾기 | 좋아요 |
|:---:|:---:|
| ![즐겨찾기](./images/favorite-1.png) | ![좋아요](./images/like-1.png) |

---

### 스마트 학습 모드

**효율적인 암기 시스템**

- ✅ **암기 모드**: O/X 체크로 틀린 카드만 반복 학습
- ✏️ **시험 모드**: 답 직접 입력 후 실력 확인
- 📝 **오답노트**: 틀린 문제 저장으로 약점 집중 공략

#### 암기 모드

| 암기 모드 화면 1 | 암기 모드 화면 2 |
|:---:|:---:|
| ![암기모드1](./images/memorize-1.png) | ![암기모드2](./images/memorize-2.png) |

#### 시험 모드

| 시험 모드 화면 1 | 시험 모드 화면 2 |
|:---:|:---:|
| ![시험모드1](./images/exam-1.png) | ![시험모드2](./images/exam-2.png) |

---

### 그룹 협업 & 권한 관리

**팀 기반 플래시카드 제작**

- 📨 **멤버 초대**: 이메일/링크로 팀원 초대
- ✋ **가입 신청**: 그룹 참여 요청 및 승인 관리
- 🔐 **RBAC 권한 체계**: Owner, Head Manager, Manager, Member 4단계 Role
- 🔒 **공개 범위 제어**: 그룹 공개/비공개 설정으로 접근 관리
- 👥 **유연한 팀 관리**: 최대 100명까지 그룹 구성 가능

| 그룹 조회 | 그룹 권한 관리 |
|:---:|:---:|
| ![그룹조회](./images/group-list-1.png) | ![그룹권한관리](./images/group-role-1.png) |

---

### 카드셋 검색 & 랭킹

**효율적인 카드셋 발견**

- 🔎 **스마트 검색**: 카드셋 이름, 해시태그 기반 검색
- 🏷️ **카테고리 필터**: 주제별 카드셋 분류 및 필터링
- 📊 **정렬**: 조회순, 좋아요순, 즐겨찾기순 정렬

| 카드셋 조회 1 | 카드셋 조회 2 | 카드셋 조회 3 |
|:---:|:---:|:---:|
| ![카드셋조회1](./images/cardset-1.png) | ![카드셋조회2](./images/cardset-2.png) | ![카드셋조회3](./images/cardset-3.png) |

---

### 회원 관리 & 마이페이지

**편리한 인증 및 알림**

- 🔑 **OAuth 소셜 로그인**: Google 계정 연동 가능
- 🔔 **실시간 알림**: 초대, 댓글, 카드셋 공유 알림
- 👤 **프로필 관리**: 내 카드셋 및 학습 기록 확인

| 마이페이지 1 | 마이페이지 2 | 마이페이지 3 |
|:---:|:---:|:---:|
| ![마이페이지1](./images/mypage-1.png) | ![마이페이지2](./images/mypage-2.png) | ![마이페이지3](./images/mypage-3.png) |

| 마이페이지 4 | 마이페이지 5 |
|:---:|:---:|
| ![마이페이지4](./images/mypage-4.png) | ![마이페이지5](./images/mypage-5.png) |

---

## 🏗️ 아키텍처

<!-- 아키텍처 다이어그램 이미지를 export하여 아래에 추가하세요 -->
<!-- excalidraw 원본: https://excalidraw.com/#room=68867f5081f6807d328f,yeabU1Xu-h5_13kS6lukIg -->

![아키텍처](이미지주소)

<details>
<summary>아키텍처 설명 펼치기</summary>

### 인프라 구성

- **클라이언트**: CloudFront + S3를 통한 정적 파일 서빙, CloudFlare DNS 관리
- **CI/CD**: GitHub Actions를 통한 자동 빌드·배포 파이프라인
- **모니터링**: Sentry를 통한 에러 트래킹 (적용 예정)

### 실시간 통신

- Socket.io 기반 WebSocket 연결로 카드 편집 실시간 동기화
- CRDT 알고리즘으로 다중 클라이언트 편집 충돌 해결

</details>

---

## 🛠️ 기술 스택

### Backend
| 분류 | 기술 |
| :--| :--- |
| | |

### Frontend

| 분류 | 기술 |
|:---|:---|
| **Framework** | React |
| **상태 관리** | Zustand |
| **HTTP 통신** | Axios |
| **스타일링** | Tailwind CSS, Radix UI |
| **실시간 통신** | Socket.io |
| **오프라인/PWA** | Service Worker |
| **해싱** | spark-md5 |

### Infra / DevOps

| 분류 | 기술 |
|:---|:---|
| **CI/CD** | GitHub Actions |
| **CDN** | CloudFront, CloudFlare |
| **스토리지** | AWS S3 |
| **모니터링** | Sentry *(적용 예정)* |

### 협업 도구

| 분류 | 기술 |
|:---|:---|
| **코드 리뷰** | CodeRabbit AI |
| **이슈 관리** | Jira |
| **커뮤니케이션** | Slack |

---

## 👨‍👩‍👧‍👦 팀원

<!-- 팀원 정보를 아래 형식으로 채워주세요 -->

| 이름 | 역할 | GitHub |
|:---:|:---:|:---:|
| 이진희 | Frontend | bebusl |
| | Backend |  |
| | Backend | |
