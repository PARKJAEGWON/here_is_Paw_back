# 여기있개 프로젝트
[사이트 바로가기](https://www.pawpaw.kknaks.site/)
[개발저장소 바로가기](https://github.com/Here-is-Paw)
## 개발기간
2025년 02월 14일 (금) ~ 03월 17일 (월)
## 프로젝트 개요
- 프로젝트 설명 : 반려견을 찾아주는 통합 플랫폼
- 문제점 :   
  기존 유기견 플랫폼은 실종된 반려견을 공고만 하고 실제적으로 발견자와 연결해주는 서비스가 없다.   
  단순게시판 형식과 실시간 소통 부족이 반려견을 찾는데 어려움이 있다고 생각.
- 해결 방안 : AI 유사도 분석, 위치기반 신고시스템, 실시간 채팅을 도입하여 반려견 실종 신고자와 발견자를 이어주는 통합 플랫폼을 개발.
## 역할 분배
#### 기능 개발에 집중하여 각자 맡은 기능의 back / front를 개발
![역할분배](https://github.com/user-attachments/assets/cd98e752-6d13-46a6-8ad5-a8b36b99f89f)
## 최종 개발 목표
#### 오버엔지니어링이지만 MSA 경험을 위해서 모놀리식에서 MSA 아키텍쳐로 분리 개발까지 해보기.
![최종 개발 목표](https://github.com/user-attachments/assets/1cf630b3-86f3-4589-93ba-760f8b788956)
## 개발 환경
### FE: 
- React: 컴포넌트 기반 UI 라이브러리
- TypeScript: 정적 타입 지원을 통한 개발 안정성 확보
- Tailwind CSS: 유틸리티 우선 CSS 프레임워크
- shadcn/ui: 재사용 가능한 UI 컴포넌트 라이브러리
- lucide-react: 아이콘 라이브러리
- Axios: HTTP 클라이언트
- Naver Maps API: 지도 표시 및 위치 기반 기능
### BE:
- 언어 & 프레임워크: Java 17, Spring Boot
- 데이터베이스: PostgreSQL, PostGIS (지리공간 데이터)
- 검색 엔진: Meilisearch
- 메시징: Kafka
- 인증: JWT, OAuth2
- 클라우드 스토리지: AWS S3
- 실시간 통신: WebSocket, SSE(Server-Sent Events)
- API 문서화: Swagger/OpenAPI
## 기획 과정
### ERD
![여기있개 ERD](https://github.com/user-attachments/assets/cf7151a9-2d51-4bbb-be91-40f28c203d38)
### 요구사항 및 API 명세서
<img width="1545" alt="스크린샷 2025-03-17 오전 11 17 21" src="https://github.com/user-attachments/assets/a6fbb540-cd00-4b6e-a6b6-34da905a750e" />

### git
![git](https://github.com/user-attachments/assets/7bce3a42-9d4b-49e2-9b78-7ee1ef25304b)
### UI Prototype
![UIPrototype](https://github.com/user-attachments/assets/4afaf789-5030-4fbc-b7de-599ca482113f)
## 아키텍쳐
#### Monolithic:
  ![시스템 아키텍쳐 Monolithic](https://github.com/user-attachments/assets/f841efb8-d442-4569-820f-9515bc229296)
#### MicroService:
  ![시스템 아키텍쳐 MicroService](https://github.com/user-attachments/assets/179966bd-dda6-4bd2-9f14-748e0843f0b5)
#### CI / CD
  ![CI/CD](https://github.com/user-attachments/assets/13d53114-0cd0-4f25-bbb3-e053f38440ef)
## 프로젝트 기능 및 구조 (MSA)
### API Gateway (포트: 8001)
[APIgateway Repo](https://github.com/Here-is-Paw/here_is_Paw_APIgateway)
- 모든 요청의 진입점 역할
- JWT 인증 및 라우팅 처리
### 회원 서비스 (포트: 8090)
[member Repo](https://github.com/Here-is-Paw/here_is_Paw_back_member)
- 회원 관리, 인증/인가
- OAuth2 로그인 지원 (카카오)
- 반려동물 정보 관리
### 게시글 서비스 (포트: 8093)
[post Repo](https://github.com/Here-is-Paw/here_is_Paw_back_post)
- 실종 동물 게시글 관리
- 발견 동물 게시글 관리
- 위치 기반 검색 기능
### 채팅 서비스 (포트: 8095)
[chat Repo](https://github.com/Here-is-Paw/here_is_Paw_back_chat)
- 실시간 채팅 기능
- WebSocket 및 STOMP 사용
- 읽지 않은 메시지 알림 기능
### 알림 서비스 (포트: 8097)
[noti Repo](https://github.com/Here-is-Paw/here_is_Paw_back_noti)
- SSE(Server-Sent Events)를 활용한 실시간 알림
- Kafka를 통한 이벤트 수신
### 결제 서비스 (포트: 8100)
[payment Repo](https://github.com/Here-is-Paw/here_is_Paw_back_payment)
- 토스페이먼츠 결제 연동
- 포인트 충전 및 사례금 지급 기능
### 검색 서비스 (포트: 8103)
[meilisearch Repo](https://github.com/Here-is-Paw/here_is_Paw_back_meilisearch)
- Meilisearch를 이용한 검색 기능
- Kafka를 통한 인덱싱 처리
### 보호소 서비스 (포트: 8105)
[careCenter Repo](https://github.com/Here-is-Paw/here_is_Paw_back_careCenter)
- 동물 보호소 정보 관리 및 제공
- 공공 API 데이터 활용
## 개요 및 기능 소개 영상
[![여기있개](http://img.youtube.com/vi/qLp-Dzk-xes/0.jpg)](https://www.youtube.com/watch?v=qLp-Dzk-xes)
