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


## 2026-07-08

### 오늘 학습한 내용

- 웹 개발 환경 구축
- VS Code 설치 및 기본 사용법
- 프로젝트 폴더 구성
- Live Server 확장 프로그램
- localhost와 포트 번호
- 정적 리소스의 개념
- HTML 기본 구조
- HTML 태그와 속성
- HTML 중첩 구조와 들여쓰기
- CSS의 역할
- CSS 선택자
- class와 id의 차이
- 외부 CSS 파일 연결
- JavaScript의 역할
- 외부 JavaScript 파일 연결
- Form과 submit 이벤트
- DOM 접근 방식
- 로그인 화면 실습
- `window.location.href`를 이용한 페이지 이동

### 오늘 정리한 문서

- [웹 개발 환경 구축](../Web-Service/05-api.md)
- [HTML, CSS, JavaScript 실습 정리](../Web-Service/06-summary.md)

### 핵심 요약

웹 개발을 하기 위해서는 코드를 작성하고 실행할 수 있는 개발 환경이 필요하다. 이번 학습에서는 VS Code를 설치하고, 프로젝트 폴더를 구성한 뒤, Live Server를 이용해 로컬 환경에서 웹 페이지를 실행하는 흐름을 정리했다.

Live Server를 사용하면 내 컴퓨터에서 간단한 웹 서버를 실행할 수 있다. 브라우저에서 `127.0.0.1:5500`과 같은 주소로 접근하면, 로컬 서버에 요청을 보내고 HTML 파일을 응답받아 화면에 표시할 수 있다. 로컬에서 실행하더라도 브라우저가 서버에 요청하고 응답을 받는 웹의 기본 구조는 동일하다.

HTML, CSS, JavaScript의 역할도 실습을 통해 정리했다. HTML은 화면의 구조를 만들고, CSS는 화면의 스타일을 적용하며, JavaScript는 사용자의 이벤트를 처리한다. 세 가지를 역할별로 분리하면 코드 관리와 유지보수가 쉬워진다.

이번 실습에서는 로그인 화면을 예시로 HTML 구조를 작성하고, CSS로 스타일을 적용한 뒤, JavaScript로 로그인 버튼 클릭 이벤트를 처리했다. 사용자가 입력한 아이디와 비밀번호를 가져와 조건에 따라 성공 시 `welcome.html`로 이동하고, 실패 시 오류 메시지를 출력하는 흐름을 확인했다.

### 헷갈린 부분

- VS Code에서 프로젝트 폴더를 여는 방식
- Live Server가 로컬 서버처럼 동작하는 원리
- `127.0.0.1`과 `localhost`의 의미
- HTML의 `head`와 `body` 영역 차이
- 태그, 속성, 속성값의 관계
- CSS 선택자에서 `.`과 `#`의 차이
- class와 id를 각각 언제 사용하는지
- 외부 CSS와 JavaScript 파일 경로 작성 방식
- `submit` 이벤트와 `event.preventDefault()`의 역할
- JavaScript에서 DOM 요소에 접근하는 방식
- `window.location.href`를 이용한 페이지 이동 방식

### 다음 학습 계획

- HTML 주요 태그 정리하기
- CSS 선택자와 박스 모델 복습하기
- JavaScript 이벤트 처리 방식 추가 정리하기
- DOM 조작 방식 복습하기
- 간단한 로그인 화면 코드를 직접 다시 작성해보기


## 2026-07-09

### 오늘 학습한 내용

- Git의 개념
- 버전 관리가 필요한 이유
- 분산 버전 관리 시스템
- Git과 GitHub의 차이
- 로컬 저장소와 원격 저장소의 차이
- CLI와 GUI 방식
- SourceTree의 역할
- Git 설치 및 버전 확인
- Git 사용자 이름과 이메일 설정
- 기본 브랜치 이름 설정
- `git init`의 역할
- `.git` 폴더의 의미
- `git status`의 역할
- `git add`와 Staging Area
- `git commit`의 역할
- `git log`를 통한 커밋 이력 확인

### 오늘 정리한 문서

- [버전 관리란?](../Git-GitHub/01-version-control.md)
- [Git 설치 및 초기 세팅](../Git-GitHub/02-install-and-setting.md)

### 핵심 요약

Git은 소스 코드의 변경 이력을 관리하기 위한 분산 버전 관리 시스템이다. 개발 프로젝트에서는 여러 사람이 함께 코드를 수정하기 때문에, 누가 어떤 내용을 수정했는지 기록하고 필요할 때 이전 상태로 되돌릴 수 있는 버전 관리가 중요하다.

Git과 GitHub는 서로 다른 개념이다. Git은 로컬 환경에서 코드의 변경 이력을 관리하는 도구이고, GitHub는 Git으로 관리되는 코드를 온라인 저장소에 올려 공유하고 협업할 수 있게 해주는 플랫폼이다.

Git은 인터넷이 없어도 로컬에서 사용할 수 있지만, GitHub는 원격 저장소를 사용하는 온라인 플랫폼이기 때문에 인터넷이 필요하다. GitHub에서는 Repository, Fork, Pull Request, Issue, Actions 같은 기능을 통해 협업과 자동화를 지원한다.

Git을 처음 사용하기 위해서는 사용자 이름과 이메일을 설정해야 한다. 이 정보는 커밋 작성자 정보로 사용된다. 또한 최근에는 기본 브랜치 이름으로 `master`보다 `main`을 많이 사용하기 때문에, `git config --global init.defaultBranch main` 명령어로 기본 브랜치 이름을 설정할 수 있다.

Git의 기본 흐름은 파일 수정 → 상태 확인 → 스테이징 → 커밋 → 이력 확인 순서로 진행된다. `git add`는 변경 사항을 Staging Area에 올리는 과정이고, `git commit`은 스테이징된 변경 사항을 하나의 버전으로 기록하는 과정이다.

### 헷갈린 부분

- Git과 GitHub의 차이
- 로컬 저장소와 원격 저장소의 차이
- CLI 방식과 GUI 방식의 차이
- SourceTree가 Git에서 어떤 역할을 하는지
- `git config --global`에서 `--global`의 의미
- `git init`을 실행했을 때 생성되는 `.git` 폴더의 역할
- `git add`와 `git commit`의 차이
- Staging Area가 필요한 이유
- `Untracked files`의 의미
- Commit Hash가 어떤 역할을 하는지
- Branch가 왜 필요한지

### 다음 학습 계획

- `git status`, `git add`, `git commit`, `git log` 명령어 반복 실습하기
- Staging Area의 역할을 예시로 다시 정리하기
- Commit 메시지 작성 규칙 정리하기
- Branch의 개념과 사용 흐름 학습하기
- GitHub 원격 저장소 연결 방식 정리하기
- `push`, `pull`, `clone` 명령어 학습하기