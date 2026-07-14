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

## 2026-07-10

### 오늘 학습한 내용

- SourceTree를 이용한 Git 이력 확인
- `.git` 폴더의 역할
- 커밋 이력과 Commit Hash
- 파일 추가, 수정, 삭제 상태 확인
- `git status`로 Git 상태 확인하기
- `git add .`와 `git add 파일명`의 차이
- `git commit -m`과 `git commit -am`의 차이
- `git log`를 통한 커밋 이력 확인
- `git reset`의 개념
- `git revert`의 개념
- reset과 revert의 차이
- Branch의 개념
- main 브랜치의 역할
- 브랜치 생성, 이동, 삭제 명령어
- `git switch -c`를 이용한 브랜치 생성 및 이동
- `git branch -d`와 `git branch -D`의 차이

### 오늘 정리한 문서

- [Commit 이해하기](../Git-GitHub/03-commit.md)
- [Branch의 개념과 활용](../Git-GitHub/04-branch.md)

### 핵심 요약

오늘은 Git에서 커밋 이력을 확인하고, 변경 사항을 추가로 기록하는 방법을 학습했다. SourceTree를 사용하면 CLI에서 `git log`로 확인하던 커밋 이력을 그래프 형태로 볼 수 있어 Git의 시간 흐름을 더 직관적으로 이해할 수 있다.

Git은 파일의 상태를 Untracked, Modified, Deleted, Staged 등으로 구분해서 관리한다. 새 파일은 Untracked 상태로 표시되고, 기존 파일을 수정하면 Modified, 삭제하면 Deleted 상태로 표시된다. 이러한 변경 사항은 `git add`를 통해 Staging Area에 올린 뒤, `git commit`으로 하나의 버전으로 기록한다.

`git commit -m`은 Staging Area에 올라간 변경 사항을 커밋할 때 사용한다. 반면 `git commit -am`은 이미 Git이 추적 중인 파일의 수정이나 삭제를 add와 commit까지 한 번에 처리할 수 있다. 다만 새로 생성된 Untracked 파일은 `git commit -am`으로 처리할 수 없기 때문에 반드시 `git add`를 먼저 해야 한다.

또한 Git에서 과거로 되돌아가는 방법으로 `reset`과 `revert`를 학습했다. `reset`은 특정 커밋으로 돌아가면서 이후 이력을 삭제할 수 있는 방식이고, `revert`는 기존 이력을 유지한 채 특정 커밋의 변경 사항을 취소하는 새 커밋을 만드는 방식이다.

마지막으로 Branch의 개념을 정리했다. Branch는 하나의 프로젝트 안에서 작업 흐름을 나누기 위한 독립적인 작업 공간이다. main 브랜치를 안정적으로 유지하면서 새로운 기능 개발이나 테스트 작업을 별도 브랜치에서 진행할 수 있다.

### 헷갈린 부분

- SourceTree에서 보이는 커밋 그래프의 의미
- `.git` 폴더를 삭제했을 때 Git 이력이 사라지는 이유
- Untracked, Modified, Deleted, Staged 상태의 차이
- `git add .`와 `git add 파일명`을 언제 구분해서 써야 하는지
- `git commit -m`과 `git commit -am`의 차이
- 새 파일이 있을 때 `git commit -am`을 사용할 수 없는 이유
- Commit Hash가 특정 커밋을 식별하는 방식
- `git log` 화면에서 `q`로 빠져나오는 방식
- `git reset --hard`가 실제 파일 상태까지 되돌리는 의미
- `reset`과 `revert`의 차이
- Branch가 왜 독립적인 작업 공간인지
- `git branch -d`와 `git branch -D`의 차이

### 다음 학습 계획

- `git status`, `git add`, `git commit`, `git log` 반복 실습하기
- SourceTree에서 커밋 이력과 변경 파일 확인해보기
- `git reset --hard`와 `git revert`의 차이를 예시로 다시 정리하기
- Branch 생성과 이동 명령어 직접 실습하기
- `git switch -c 브랜치명` 명령어 익숙해지기
- main 브랜치와 feature 브랜치의 관계 정리하기
- 이후 Merge와 Pull Request 개념 학습하기


## 2026-07-12

### 오늘 학습한 내용

- Git 브랜치 생성과 이동
- 여러 브랜치에서 독립적으로 작업하는 흐름
- SourceTree를 이용한 브랜치 흐름 확인
- `git log --all --decorate --oneline --graph` 명령어
- Merge의 개념
- Rebase의 개념
- Fast-forward의 의미
- Merge와 Rebase의 차이
- 병합 완료 후 브랜치 삭제
- Merge Conflict의 개념
- Conflict 발생 상황
- Conflict 해결 흐름
- 원격 저장소의 개념
- 로컬 저장소와 원격 저장소의 차이
- `git remote`, `git push`, `git pull`, `git clone`의 역할
- Pull Request 기반 협업 흐름

### 오늘 정리한 문서

- [Merge, Rebase, Conflict 이해하기](../Git-GitHub/05-merge-conflict.md)
- [Remote Repository 이해하기](../Git-GitHub/06-remote-repository.md)

### 핵심 요약

오늘은 Git에서 브랜치를 생성하고, 서로 다른 브랜치에서 작업한 내용을 하나로 합치는 방법을 학습했다. 브랜치는 하나의 프로젝트 안에서 독립적인 작업 공간을 만드는 기능이다. main 브랜치를 안정적으로 유지하면서 새로운 기능 개발이나 테스트 작업을 별도 브랜치에서 진행할 수 있다.

브랜치를 합치는 방법에는 Merge와 Rebase가 있다. Merge는 두 브랜치를 병합 커밋으로 합치는 방식이며, 브랜치의 작업 흐름이 이력에 남는다. Rebase는 한 브랜치의 커밋을 다른 브랜치 뒤에 이어 붙이는 방식이며, 커밋 이력을 한 줄로 깔끔하게 정리할 수 있다.

Rebase 이후에는 main 브랜치의 위치를 최신 커밋으로 이동시키기 위해 Fast-forward가 발생할 수 있다. Fast-forward는 새로운 병합 커밋을 만들지 않고 브랜치 포인터만 앞으로 이동하는 방식이다.

브랜치를 병합하는 과정에서는 Conflict가 발생할 수 있다. Conflict는 서로 다른 브랜치에서 같은 파일의 같은 부분을 수정했을 때 Git이 자동으로 병합하지 못하는 상황이다. 이 경우 개발자가 직접 파일을 열어 어떤 내용을 남길지 결정하고, 충돌 표시를 제거한 뒤 다시 add와 commit을 해야 한다.

또한 원격 저장소의 개념도 함께 정리했다. Git은 로컬에서 버전 관리를 수행하는 도구이고, GitHub는 Git 저장소를 온라인에서 관리하고 협업할 수 있도록 도와주는 플랫폼이다. 로컬 저장소의 커밋을 GitHub에 올릴 때는 push를 사용하고, GitHub의 변경 사항을 로컬로 가져올 때는 pull 또는 clone을 사용한다.

### 헷갈린 부분

- 브랜치가 독립적인 작업 공간이라는 의미
- SourceTree에서 브랜치가 분기되는 그래프를 해석하는 방법
- `git log --all --decorate --oneline --graph` 옵션의 의미
- Merge와 Rebase의 차이
- Rebase 이후 Fast-forward가 필요한 이유
- 병합이 끝난 브랜치를 삭제해도 작업 내용이 사라지지 않는 이유
- Conflict가 발생하는 정확한 상황
- Conflict 표시에서 `HEAD`가 의미하는 것
- Conflict 해결 후 `git add`를 다시 해야 하는 이유
- 로컬 저장소와 원격 저장소의 차이
- `git push`, `git pull`, `git fetch`, `git clone`의 차이
- Pull Request가 필요한 이유

### 다음 학습 계획

- Merge와 Rebase 명령어 직접 반복 실습하기
- SourceTree에서 병합 커밋과 Rebase 결과 비교하기
- Conflict 상황을 직접 만들어보고 해결해보기
- `git remote -v`로 원격 저장소 연결 상태 확인하기
- 로컬 저장소와 GitHub 원격 저장소 연결 실습하기
- `git push`, `git pull`, `git clone` 명령어 실습하기
- Pull Request 기반 협업 흐름 정리하기

## 2026-07-13

### 오늘 학습한 내용

- Git 충돌이 발생하는 상황
- Merge Conflict 해결 방법
- Rebase Conflict 해결 방법
- Current Change와 Incoming Change의 의미
- `git merge --abort`의 역할
- `git rebase --continue`의 역할
- `git rebase --abort`의 역할
- Git과 GitHub의 차이
- 로컬 저장소와 원격 저장소의 차이
- GitHub Repository 생성과 게시
- VS Code에서 GitHub로 프로젝트 올리기
- `git remote -v`로 원격 저장소 확인하기
- `origin`의 의미
- `git push`의 역할
- `git pull`의 역할
- `git clone`의 역할
- push 전에 pull이 필요한 상황
- GitHub 협업 시나리오
- Pull Request 기반 협업 흐름

### 오늘 정리한 문서

- [Push와 Pull 이해하기](../Git-GitHub/07-push-pull.md)
- [GitHub 협업 시나리오 정리](../Git-GitHub/08-collaboration-scenario.md)

### 핵심 요약

오늘은 Git에서 충돌이 발생하는 상황과 GitHub 원격 저장소를 사용하는 흐름을 학습했다. 충돌은 서로 다른 브랜치에서 같은 파일의 같은 부분을 다르게 수정했을 때 발생한다. Git은 어떤 내용을 최종 결과로 선택해야 하는지 자동으로 판단할 수 없기 때문에 개발자가 직접 충돌을 해결해야 한다.

Merge 과정에서 충돌이 발생하면 충돌 파일을 수정한 뒤 `git add`와 `git commit`을 통해 병합을 완료한다. 반면 Rebase 과정에서 충돌이 발생하면 충돌 파일을 수정하고 `git add`를 한 뒤 `git rebase --continue`를 실행해야 한다. 해결이 어렵다면 merge는 `git merge --abort`, rebase는 `git rebase --abort`로 중단할 수 있다.

또한 GitHub 원격 저장소를 사용하는 방법을 정리했다. Git은 로컬에서 버전 관리를 수행하는 도구이고, GitHub는 Git 저장소를 온라인에서 관리하고 협업할 수 있도록 도와주는 플랫폼이다. 로컬에서 만든 커밋을 GitHub에 반영하려면 `git push`를 사용하고, GitHub의 변경 사항을 로컬로 가져오려면 `git pull`을 사용한다.

협업에서는 로컬 저장소와 원격 저장소의 상태를 계속 맞추는 것이 중요하다. 원격 저장소에 내 로컬에는 없는 최신 커밋이 존재하는 상태에서 바로 push를 시도하면 push가 거부될 수 있다. 이 경우 먼저 pull을 통해 원격 변경 사항을 가져온 뒤 다시 push해야 한다.

마지막으로 GitHub 협업 흐름을 정리했다. 일반적으로 main 브랜치에서 직접 작업하지 않고, 기능별 브랜치를 생성해 작업한 뒤 push하고 Pull Request를 생성한다. 이후 코드 리뷰를 거쳐 main 브랜치에 병합하는 방식이 안정적인 협업 흐름이다.

### 헷갈린 부분

- Merge Conflict와 Rebase Conflict의 차이
- Current Change와 Incoming Change의 기준
- `HEAD`가 현재 브랜치를 의미한다는 점
- Merge 충돌 해결 후에는 `git commit`을 해야 하는 점
- Rebase 충돌 해결 후에는 `git rebase --continue`를 해야 하는 점
- `git merge --abort`와 `git rebase --abort`의 차이
- Git과 GitHub의 역할 차이
- 로컬 저장소와 원격 저장소의 차이
- `origin`이 기본 원격 저장소 이름이라는 점
- `git push`와 `git pull`의 방향 차이
- 원격 저장소에 최신 커밋이 있을 때 push가 거부되는 이유
- pull 과정에서도 충돌이 발생할 수 있다는 점
- Pull Request가 단순 병합 요청이 아니라 코드 리뷰 흐름이라는 점

### 다음 학습 계획

- Merge Conflict 상황 직접 만들어보고 해결하기
- Rebase Conflict 해결 흐름 다시 실습하기
- `git remote -v` 결과 해석 연습하기
- GitHub 원격 저장소에 직접 push 해보기
- GitHub에서 수정한 내용을 로컬로 pull 해보기
- push 거부 상황을 예시로 다시 정리하기
- Pull Request 생성 흐름 정리하기
- 협업 시 main 브랜치와 feature 브랜치 운영 방식 복습하기

## 2026-07-14

### 오늘 학습한 내용

- Java를 배우는 이유
- Python과 Java의 사용 분야 차이
- Java와 백엔드 개발의 관계
- Spring Boot와 Java의 관계
- 객체 지향 프로그래밍의 개념
- Class와 Instance의 차이
- Variable과 Method의 역할
- JDK, JRE, JVM의 관계
- JVM과 플랫폼 독립성
- JDK 17 설치 흐름
- `JAVA_HOME` 환경 변수 설정
- PATH 환경 변수와 JDK `bin` 경로
- `java`와 `javac` 명령어
- Java 소스 코드 컴파일 과정
- `.java`, `.class`, Bytecode의 관계
- Java 대소문자 구분
- Java 식별자 네이밍 규칙
- VS Code Java 확장 설치
- `GreetingApp.java` 작성과 실행
- `main` 메서드의 역할
- `System.out.println()` 출력문

### 오늘 정리한 문서

- [Java 개발 환경 세팅](../Java/01-environment-setting.md)
- [Java 변수와 기본 구조](../Java/02-variable-and-type.md)

### 핵심 요약

오늘은 Java 학습을 시작하면서 Java가 어떤 분야에서 사용되는지와 개발 환경을 어떻게 구성하는지 학습했다.

Python은 인공지능과 데이터 분석 분야에서 많이 사용되고, Java는 백엔드와 기업 시스템에서 많이 사용된다. 특히 국내 공공기관, 금융권, 기업 내부 시스템에서는 Java 기반 백엔드가 많이 사용되며, Spring Boot는 Java 기반 웹 애플리케이션을 만들 때 사용하는 대표적인 프레임워크이다.

Java는 객체 지향 프로그래밍 언어이다. 객체 지향에서는 현실 세계의 객체를 프로그램 안에서 표현하기 위해 Class를 사용한다. Class는 객체를 만들기 위한 설계도이고, Class를 바탕으로 실제 프로그램 안에서 생성된 객체를 Instance라고 한다. 객체의 명사적인 특징은 Variable로 표현하고, 동작이나 행위는 Method로 표현한다.

Java 개발을 위해서는 JDK가 필요하다. JDK는 Java Development Kit의 약자이며, Java 개발에 필요한 도구를 포함한다. JDK 안에는 Java 실행 환경인 JRE가 포함되고, Java 프로그램은 JVM 위에서 실행된다. JVM이 설치된 환경이라면 운영체제에 관계없이 Java 프로그램을 실행할 수 있다는 점에서 Java는 플랫폼 독립성을 가진다.

개발 환경 세팅에서는 Eclipse Adoptium의 Temurin JDK 17을 설치하고, `JAVA_HOME` 환경 변수와 PATH 설정을 확인했다. PATH에 JDK의 `bin` 경로가 등록되어 있어야 터미널에서 `java`, `javac` 명령어를 사용할 수 있다.

또한 VS Code에서 Java Extension Pack을 설치하고 `GreetingApp.java` 파일을 작성했다. Java에서는 public class 이름과 파일 이름이 같아야 하며, 프로그램은 `main` 메서드에서 실행을 시작한다. `System.out.println()`을 사용하면 콘솔에 문자열을 출력할 수 있다.

### 헷갈린 부분

- Java와 Python의 사용 분야 차이
- Java가 백엔드에서 많이 사용되는 이유
- 객체 지향 프로그래밍의 정확한 의미
- Class와 Instance의 차이
- Variable과 Method의 차이
- JDK, JRE, JVM의 포함 관계
- JVM 위에서 Java 프로그램이 실행된다는 의미
- `JAVA_HOME`을 설정하는 이유
- PATH에 JDK `bin` 경로가 필요한 이유
- `javac`와 `java` 명령어의 차이
- `.java` 파일과 `.class` 파일의 차이
- Bytecode가 JVM에서 실행된다는 의미
- Java가 대소문자를 구분한다는 점
- public class 이름과 파일 이름이 같아야 하는 이유
- `main` 메서드가 실행 시작점이라는 의미

### 다음 학습 계획

- Java 변수 선언과 초기화 문법 복습하기
- Java 기본 자료형 정리하기
- `int`, `double`, `boolean`, `char`, `String` 차이 정리하기
- Class와 Instance 예시 직접 작성해보기
- `javac`와 `java` 명령어로 직접 컴파일과 실행 실습하기
- VS Code에서 Java 파일 생성과 실행 반복하기
- Java 네이밍 규칙 다시 정리하기
- main 메서드 구조 암기하기