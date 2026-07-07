# Daily Log

## 2026-07-06

### 오늘 학습한 내용

- 웹 서비스의 기본 구조
- 클라이언트와 서버의 역할
- 프론트엔드와 백엔드의 차이
- 데이터베이스의 역할
- Request와 Response 흐름
- URL, HTTP, HTTPS의 개념
- 웹 서버와 WAS의 차이
- API와 API 명세의 필요성

### 오늘 정리한 문서

- [웹 서비스 기본 개념](../Web-Service/01-basic-concept.md)
- [클라이언트와 서버](../Web-Service/02-client-server.md)

### 핵심 요약

웹 서비스는 사용자가 브라우저를 통해 요청을 보내고, 서버가 요청을 처리한 뒤 응답을 반환하는 구조로 동작한다.

사용자는 백엔드나 데이터베이스에 직접 접근하지 않고, 프론트엔드 화면을 통해 이벤트를 발생시킨다. 이 요청은 백엔드로 전달되고, 백엔드는 필요한 비즈니스 로직을 처리한 뒤 데이터베이스와 통신하여 결과를 반환한다.

이번 학습을 통해 웹 서비스는 단순히 화면만 의미하는 것이 아니라, 클라이언트, 프론트엔드, 백엔드, 데이터베이스, 서버가 요청과 응답을 중심으로 연결된 구조라는 것을 이해했다.

### 헷갈린 부분

- 웹 서버와 WAS의 차이
- DB와 DBMS의 차이
- JDBC, ORM, JPA의 관계
- API와 URL의 차이

### 다음 학습 계획

- HTTP Method 정리하기
- API 요청과 응답 구조 정리하기
- 웹 서비스 전체 흐름을 그림으로 다시 정리하기


## 2026-07-07

### 오늘 학습한 내용

- 웹 개발에 필요한 기본 요소
- Java와 Python의 활용 분야 차이
- IDE의 역할
- Request와 Response의 상세 구조
- CRUD의 개념
- HTTP Method의 종류
- Header와 Body의 차이
- JSON 요청/응답 형식
- Status Code의 의미
- API URL 네이밍 규칙
- 프론트엔드 기술 스택
- HTML, CSS, JavaScript의 역할
- JSP와 ASP의 개념
- 반응형 웹과 Bootstrap
- SPA의 개념
- React와 Vue의 차이
- Library와 Framework의 차이

### 오늘 정리한 문서

- [웹의 동작 방식](../Web-Service/03-how-web-works.md)
- [프론트엔드 기술 스택과 SPA 구조](../Web-Service/04-network-structure.md)

### 핵심 요약

웹 서비스는 Request와 Response를 중심으로 동작하며, 사용자의 요청은 HTTP Method를 통해 목적이 구분된다.

CRUD는 Create, Read, Update, Delete를 의미하며, 각각 POST, GET, PUT/PATCH, DELETE와 연결해서 이해할 수 있다. Request는 Header와 Body로 구성될 수 있고, Header에는 요청에 대한 메타 정보가, Body에는 서버에 전달할 실제 데이터가 담긴다.

프론트엔드 영역에서는 HTML, CSS, JavaScript가 기본 기술 스택으로 사용된다. HTML은 구조, CSS는 스타일, JavaScript는 동작을 담당한다. 최근에는 React나 Vue 같은 기술을 활용해 SPA 방식으로 화면을 구성하는 경우가 많다.

SPA는 하나의 페이지를 기반으로 필요한 데이터만 서버에 요청하고 화면 일부를 갱신하는 방식이다. 이를 통해 페이지 전환이 빠르고 사용자 경험이 자연스러워질 수 있지만, 초기 로딩 속도나 SEO 측면에서는 추가적인 고려가 필요하다.

이번 학습을 통해 웹 요청과 응답이 단순히 데이터를 주고받는 것이 아니라, URL, HTTP Method, Header, Body, Status Code, JSON 형식, API 명세와 함께 체계적으로 설계되어야 한다는 것을 이해했다.

### 헷갈린 부분

- GET, POST, PUT, PATCH, DELETE의 정확한 사용 기준
- PUT과 PATCH의 차이
- Header와 Body에 각각 어떤 값을 넣어야 하는지
- Status Code 200, 201, 204의 차이
- API URL을 명사형 복수로 작성하는 이유
- SPA와 기존 웹 페이지 방식의 차이
- React가 라이브러리이고 Vue가 프레임워크로 분류되는 이유

### 다음 학습 계획

- HTTP Method별 예시 더 정리하기
- Request Header와 Body 예시 직접 작성해보기
- JSON 형식에 익숙해지기
- Status Code 주요 번호 정리하기
- React와 Vue의 컴포넌트 구조 비교하기