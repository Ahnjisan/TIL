# 웹의 동작 방식: 요청과 응답

## 1. 웹 개발에 필요한 기본 요소

웹 개발을 하기 위해서는 먼저 개발 언어를 선택해야 한다.

대표적으로 Java와 Python이 있다.

Java는 기업용 웹 서비스, 공공기관, 금융권 시스템 등 상업용 애플리케이션 개발에서 많이 사용된다.  
반면 Python은 데이터 분석, 시각화, 인공지능, 머신러닝 분야에서 많이 활용된다.

웹 개발을 위해 필요한 기본 요소는 다음과 같다.

| 요소 | 설명 |
|---|---|
| 개발 언어 | 웹 애플리케이션을 구현하기 위한 언어 |
| IDE | 코드를 작성하고 실행하기 위한 통합 개발 환경 |
| 웹 서버 | 정적 리소스를 처리하는 서버 |
| WAS | 동적 애플리케이션 로직을 처리하는 서버 |

IDE는 Integrated Development Environment의 약자이다.  
코드 작성, 실행, 빌드, 디버깅, 터미널 사용 등을 하나의 환경에서 할 수 있도록 도와주는 개발 도구이다.

## 2. 웹은 요청과 응답으로 동작한다

웹 서비스는 기본적으로 Request와 Response 구조로 동작한다.

클라이언트가 서버에 요청을 보내면, 서버는 요청을 처리한 뒤 응답을 반환한다.

```text
Client
→ Request
→ Server
→ Response
→ Client
```

즉, 웹 서비스는 요청과 응답이 반복되면서 동작하는 구조이다.

## 3. CRUD

CRUD는 사용자가 서버에 요청할 수 있는 대표적인 데이터 처리 행위를 의미한다.

CRUD는 Create, Read, Update, Delete의 약자이다.

| CRUD | 의미 | 설명 |
|---|---|---|
| Create | 생성 | 새로운 데이터를 만든다 |
| Read | 조회 | 데이터를 읽거나 가져온다 |
| Update | 수정 | 기존 데이터를 변경한다 |
| Delete | 삭제 | 기존 데이터를 제거한다 |

예를 들어 게시판 서비스를 기준으로 보면 다음과 같다.

```text
게시글 작성 → Create
게시글 조회 → Read
게시글 수정 → Update
게시글 삭제 → Delete
```

웹 서비스에서 사용자가 하는 대부분의 동작은 CRUD로 정리할 수 있다.

## 4. HTTP Method

클라이언트가 서버에 요청을 보낼 때는 요청 목적에 맞는 HTTP Method를 사용한다.

CRUD는 HTTP Method와 연결해서 이해할 수 있다.

| CRUD | HTTP Method | 의미 |
|---|---|---|
| Create | POST | 데이터 생성 |
| Read | GET | 데이터 조회 |
| Update | PUT / PATCH | 데이터 수정 |
| Delete | DELETE | 데이터 삭제 |

PUT은 전체 수정을 의미하는 경우가 많고, PATCH는 일부 수정을 의미하는 경우가 많다.

예시는 다음과 같다.

```text
GET /users
POST /users
PUT /users/1
PATCH /users/1
DELETE /users/1
```

HTTP Method는 서버에 어떤 목적의 요청을 보내는지 나타내는 방식이다.

## 5. Request의 구조

클라이언트가 서버에 보내는 Request는 크게 Header와 Body로 나눌 수 있다.

| 구분 | 설명 |
|---|---|
| Header | 요청에 대한 메타 정보 |
| Body | 서버에 전달할 실제 데이터 |

Header에는 요청 데이터의 형식, 인증 정보, 응답 형식과 같은 부가 정보가 담긴다.

예시는 다음과 같다.

```text
Content-Type: application/json
Authorization: Bearer token
```

Body에는 서버에 전달할 실제 데이터가 담긴다.

예를 들어 로그인 요청의 Body는 다음과 같이 작성할 수 있다.

```json
{
  "email": "user@example.com",
  "password": "1234"
}
```

정리하면 Header는 요청에 대한 설명 정보이고, Body는 실제 데이터 영역이다.

## 6. URL 네이밍 규칙

API URL을 작성할 때는 일정한 규칙을 지키는 것이 좋다.

일반적으로 URL은 동사보다 명사 중심으로 작성한다.  
또한 리소스는 복수형으로 표현하는 경우가 많다.

| 좋지 않은 예 | 좋은 예 |
|---|---|
| `/getUser` | `/users` |
| `/createPost` | `/posts` |
| `/deleteComment` | `/comments/{commentId}` |

특정 사용자의 게시글을 표현할 때는 계층 구조를 사용할 수 있다.

```text
/users/{userId}/posts/{postId}
```

URL은 리소스를 표현하고, 실제 행위는 HTTP Method로 표현하는 것이 일반적이다.

## 7. JSON

JSON은 JavaScript Object Notation의 약자이다.

JSON은 데이터를 Key-Value 형식으로 표현하는 방식이다.  
프론트엔드와 백엔드가 데이터를 주고받을 때 많이 사용된다.

예시는 다음과 같다.

```json
{
  "name": "Jisan",
  "age": 26,
  "role": "developer"
}
```

React나 Vue 같은 SPA 기반 프론트엔드에서는 백엔드 API와 JSON 형식으로 데이터를 주고받는 경우가 많다.

## 8. HTTP와 HTTPS

HTTP는 클라이언트와 서버가 웹에서 데이터를 주고받기 위한 통신 프로토콜이다.

하지만 HTTP는 데이터가 암호화되지 않기 때문에 보안에 취약할 수 있다.  
이를 보완한 것이 HTTPS이다.

| 구분 | 설명 |
|---|---|
| HTTP | 웹 통신을 위한 기본 프로토콜 |
| HTTPS | HTTP에 보안 기능이 추가된 프로토콜 |

HTTPS는 데이터를 암호화하여 전송한다.

따라서 금융, 공공기관, 쇼핑몰처럼 민감한 데이터를 다루는 서비스에서는 HTTPS 사용이 중요하다.

## 9. Response의 구조

서버는 클라이언트의 요청을 처리한 뒤 Response를 반환한다.

Response에도 Header와 Body가 포함될 수 있다.  
또한 요청 처리 결과를 알려주는 Status Code가 함께 전달된다.

대표적인 상태 코드는 다음과 같다.

| 상태 코드 | 의미 |
|---|---|
| 200 | 요청 성공 |
| 201 | 생성 성공 |
| 204 | 성공했지만 응답 데이터 없음 |
| 400번대 | 클라이언트 요청 오류 |
| 500번대 | 서버 내부 오류 |

예를 들어 요청이 정상적으로 처리되면 200번대 응답이 반환된다.  
요청 자체에 문제가 있으면 400번대 오류가 발생할 수 있고, 서버 내부에서 문제가 발생하면 500번대 오류가 발생할 수 있다.

## 10. API 명세

프론트엔드와 백엔드가 함께 개발하기 위해서는 API 명세가 필요하다.

API 명세는 클라이언트와 서버가 어떤 방식으로 요청과 응답을 주고받을지 정리한 문서이다.

API 명세에는 보통 다음 내용이 포함된다.

| 항목 | 설명 |
|---|---|
| URL | 요청 주소 |
| Endpoint | API 접근 지점 |
| HTTP Method | 요청 방식 |
| Request Header | 요청 헤더 정보 |
| Request Body | 요청 데이터 |
| Response Body | 응답 데이터 |
| Status Code | 응답 상태 코드 |
| Error Message | 오류 메시지 |

예를 들어 로그인 API 명세는 다음과 같이 작성할 수 있다.

```text
API 이름: 로그인
URL: /api/login
Method: POST
Request Body: email, password
Response: 로그인 성공 여부, 메시지
```

API 명세가 명확하면 프론트엔드와 백엔드가 같은 기준으로 개발할 수 있다.

## 11. 전체 흐름 정리

웹에서 요청과 응답이 처리되는 흐름은 다음과 같다.

```text
사용자
→ 브라우저
→ 프론트엔드에서 요청 생성
→ HTTP / HTTPS Request
→ 백엔드 서버
→ 요청 처리
→ 데이터베이스 접근
→ Response 생성
→ 프론트엔드로 응답 반환
→ 화면에 결과 표시
```

웹 서비스는 결국 클라이언트가 요청을 보내고, 서버가 요청을 처리한 뒤 응답을 반환하는 구조로 동작한다.

이때 요청에는 URL, HTTP Method, Header, Body가 포함될 수 있고, 응답에는 Status Code, Header, Body가 포함될 수 있다.

## 12. 정리

이번 학습에서는 웹의 요청과 응답 구조를 더 자세히 학습했다.

핵심 개념은 다음과 같다.

- 웹은 Request와 Response를 중심으로 동작한다.
- CRUD는 Create, Read, Update, Delete를 의미한다.
- CRUD는 HTTP Method와 연결해서 이해할 수 있다.
- Request는 Header와 Body로 구성될 수 있다.
- Header는 메타 정보, Body는 실제 데이터를 담는다.
- API URL은 명사형 리소스 중심으로 작성하는 것이 좋다.
- JSON은 프론트엔드와 백엔드가 데이터를 주고받을 때 많이 사용된다.
- HTTP보다 HTTPS가 보안성이 높다.
- Response에는 Status Code가 포함되어 요청 처리 결과를 알려준다.
- API 명세는 프론트엔드와 백엔드 협업을 위해 필요하다.