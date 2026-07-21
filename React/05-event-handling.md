# React Event 처리와 Router 활용

## 1. Event 처리란?

Event 처리는 사용자의 행동에 반응하는 로직을 작성하는 것이다.

웹 화면에서 사용자는 input에 값을 입력하거나, 버튼을 클릭하거나, form을 제출할 수 있다.

React에서는 이러한 사용자 행동을 이벤트로 처리한다.

대표적인 이벤트는 다음과 같다.

| 이벤트 | 설명 |
|---|---|
| onChange | input 값이 변경될 때 실행 |
| onSubmit | form이 제출될 때 실행 |
| onClick | 버튼이나 요소를 클릭할 때 실행 |

## 2. onChange

`onChange`는 input 값이 바뀔 때 실행되는 이벤트이다.

로그인 화면에서는 아이디와 비밀번호 입력값을 State로 관리하기 위해 사용한다.

예시는 다음과 같다.

    <input
        type="text"
        value={userId}
        onChange={(event) => setUserId(event.target.value)}
    />

사용자가 input에 값을 입력하면 `event.target.value`를 통해 입력값을 가져올 수 있다.

그 값을 `setUserId`에 전달하면 State가 변경된다.

## 3. onSubmit

`onSubmit`은 form이 제출될 때 실행되는 이벤트이다.

로그인 버튼의 타입이 `submit`이면 버튼 클릭 시 form의 submit 이벤트가 발생한다.

예시는 다음과 같다.

    <form onSubmit={handleSubmit}>
        ...
        <button type="submit">로그인</button>
    </form>

사용자가 로그인 버튼을 누르면 `handleSubmit` 함수가 실행된다.

## 4. Event Handler

Event Handler는 이벤트 발생 시 실행되는 함수이다.

예시는 다음과 같다.

    const handleSubmit = (event) => {
        event.preventDefault();
        console.log("로그인 요청");
    };

이 함수는 form 제출 이벤트가 발생했을 때 실행된다.

React에서는 보통 `handle`로 시작하는 이름을 이벤트 핸들러 함수에 사용한다.

예를 들어 `handleSubmit`, `handleLogout`, `handleChange` 같은 이름을 사용할 수 있다.

## 5. preventDefault

HTML form은 기본적으로 submit 이벤트가 발생하면 페이지를 새로고침한다.

React에서는 페이지 새로고침 없이 Component 내부에서 직접 로직을 처리하는 경우가 많다.

따라서 submit 이벤트 핸들러에서 `event.preventDefault()`를 호출한다.

    const handleSubmit = (event) => {
        event.preventDefault();
    };

이 코드를 작성하면 form의 기본 제출 동작을 막고, React 이벤트 처리 로직만 실행할 수 있다.

## 6. 로그인 이벤트 처리 흐름

로그인 이벤트 처리 흐름은 다음과 같다.

    아이디 입력
    → onChange로 userId State 변경

    비밀번호 입력
    → onChange로 password State 변경

    로그인 버튼 클릭
    → onSubmit 이벤트 발생

    handleSubmit 실행
    → preventDefault로 기본 동작 차단
    → 입력값 검증
    → 성공 또는 실패 처리

이 흐름을 통해 React에서는 화면 입력값과 이벤트 로직을 연결할 수 있다.

## 7. Validation

Validation은 사용자 입력값을 검증하는 과정이다.

로그인 화면에서는 아이디와 비밀번호가 모두 입력되었는지 확인할 수 있다.

예시는 다음과 같다.

    if (!userId || !password) {
        setError("아이디와 비밀번호를 모두 입력해 주세요.");
        return;
    }

입력값이 비어 있으면 에러 메시지를 State에 저장하고, 이후 로직을 중단한다.

## 8. 로그인 성공과 실패 처리

백엔드가 없는 상태에서는 임시 로그인 검증을 사용할 수 있다.

예를 들어 다음 조건을 사용할 수 있다.

    userId === "admin"
    password === "1234"

로그인에 성공하면 alert를 띄우고, 실패하면 에러 메시지를 출력할 수 있다.

    if (userId === "admin" && password === "1234") {
        alert("로그인 성공");
    } else {
        setError("아이디 또는 비밀번호가 올바르지 않습니다.");
    }

실제 프로젝트에서는 이 검증을 프론트엔드가 직접 하지 않고 백엔드 로그인 API를 호출해야 한다.

## 9. Axios를 이용한 API 요청

백엔드가 준비되어 있다면 Axios를 이용해 로그인 API를 호출할 수 있다.

설치 명령어는 다음과 같다.

    npm install axios

사용할 파일에서 import한다.

    import axios from "axios";

POST 요청 예시는 다음과 같다.

    const response = await axios.post("/api/login", {
        userId: userId,
        password: password
    });

이때 아이디와 비밀번호는 JSON 형식으로 백엔드에 전달된다.

## 10. 비동기 통신

API 요청은 비동기로 처리된다.

비동기 통신에서는 요청을 보낸 뒤 응답이 올 때까지 시간이 걸릴 수 있다.

이때 `async`와 `await`를 사용하면 응답을 기다린 뒤 다음 로직을 실행할 수 있다.

    const handleSubmit = async (event) => {
        event.preventDefault();

        const response = await axios.post("/api/login", {
            userId,
            password
        });
    };

`async`는 비동기 함수임을 의미하고, `await`는 비동기 요청의 결과를 기다린다는 의미이다.

## 11. token 저장

로그인 성공 시 백엔드가 token을 응답할 수 있다.

프론트엔드는 이 token을 저장해 이후 인증이 필요한 요청에 사용할 수 있다.

예시는 다음과 같다.

    const token = response.data.token;
    localStorage.setItem("token", token);

`localStorage`는 브라우저에 데이터를 저장하는 공간이다.

다만 실제 서비스에서는 token을 어디에 저장할지 보안 관점에서 신중하게 결정해야 한다.

## 12. React Router DOM

React에서 Component 간 이동을 구현하려면 React Router DOM을 사용할 수 있다.

설치 명령어는 다음과 같다.

    npm install react-router-dom

React Router DOM은 URL 경로와 Component를 연결해주는 라이브러리이다.

예를 들어 `/` 경로는 Login Component, `/welcome` 경로는 Welcome Component로 연결할 수 있다.

## 13. App.js Router 설정

라우터 설정은 `App.js`에서 구성할 수 있다.

필요한 항목은 다음과 같다.

    BrowserRouter
    Routes
    Route

예시 구조는 다음과 같다.

    <Router>
        <Routes>
            <Route path="/" element={<Login />} />
            <Route path="/welcome" element={<Welcome />} />
        </Routes>
    </Router>

`Route` 하나는 하나의 경로와 하나의 Component를 연결한다.

## 14. useNavigate

`useNavigate`는 React Router DOM에서 제공하는 Hook이다.

특정 이벤트가 발생했을 때 다른 경로로 이동하고 싶을 때 사용한다.

예시는 다음과 같다.

    const moveUrl = useNavigate();

    moveUrl("/welcome");

로그인 성공 후 Welcome 페이지로 이동할 때 사용할 수 있다.

## 15. state를 전달하며 이동하기

`useNavigate`를 사용할 때 이동할 경로와 함께 state 값을 전달할 수 있다.

예시는 다음과 같다.

    moveUrl("/welcome", {
        state: {
            userName: userId
        }
    });

이 코드는 `/welcome` 경로로 이동하면서 `userName`이라는 이름으로 사용자 아이디를 전달한다.

## 16. useLocation

`useLocation`은 현재 경로 정보와 함께 전달된 state 값을 확인할 때 사용한다.

Welcome Component에서 Login Component가 전달한 값을 받을 수 있다.

예시는 다음과 같다.

    const location = useLocation();
    const userName = location.state?.userName || "Guest";

전달된 userName이 있으면 해당 값을 사용하고, 없으면 `"Guest"`를 기본값으로 사용할 수 있다.

## 17. Welcome Component

Welcome Component는 로그인 성공 후 이동하는 페이지 역할을 한다.

화면에는 로그인 성공 메시지와 사용자 이름을 보여줄 수 있다.

또한 로그아웃 버튼을 만들고, 클릭하면 다시 로그인 페이지로 이동시킬 수 있다.

    const handleLogout = () => {
        moveUrl("/");
    };

로그아웃 버튼에는 `onClick` 이벤트를 연결한다.

    <button onClick={handleLogout}>로그아웃</button>

## 18. Inline Style

React에서는 Component 안에서 객체 형태로 스타일을 작성할 수 있다.

이를 Inline Style이라고 한다.

예시는 다음과 같다.

    const containerStyle = {
        textAlign: "center",
        marginTop: "100px"
    };

JSX에서는 다음과 같이 적용할 수 있다.

    <div style={containerStyle}>
        ...
    </div>

CSS 파일을 분리해서 적용할 수도 있고, 간단한 스타일은 Inline Style로 처리할 수도 있다.

## 19. 페이지 이동 흐름

로그인 성공 후 페이지 이동 흐름은 다음과 같다.

    사용자가 아이디와 비밀번호 입력
    → 로그인 버튼 클릭
    → handleSubmit 실행
    → 로그인 검증 성공
    → useNavigate로 /welcome 이동
    → state로 userName 전달
    → Welcome Component에서 useLocation으로 userName 수신
    → 환영 메시지 출력

로그아웃 흐름은 다음과 같다.

    로그아웃 버튼 클릭
    → handleLogout 실행
    → useNavigate로 / 이동
    → Login Component 렌더링

## 20. index.js와 App.js 역할

라우터를 사용하면 `index.js`에서는 App Component를 렌더링한다.

그리고 App Component 안에서 Router 설정을 관리한다.

흐름은 다음과 같다.

    index.html
    → root 영역 제공

    index.js
    → App Component 렌더링

    App.js
    → Router 설정

    Route
    → 경로에 맞는 Component 렌더링

따라서 라우터를 사용하는 경우 App Component는 전체 화면 전환 구조를 담당한다.

## 21. 전체 이벤트 처리 흐름

이번 실습 전체 흐름은 다음과 같다.

    Login.jsx 작성
    → input State 관리
    → onChange 이벤트 연결
    → onSubmit 이벤트 연결
    → Validation 처리
    → 로그인 성공 시 useNavigate로 이동
    → Welcome.jsx 작성
    → useLocation으로 전달받은 값 사용
    → 로그아웃 버튼 onClick 처리
    → useNavigate로 로그인 페이지 이동

이 흐름을 통해 React에서 State, Event, Router가 어떻게 연결되는지 확인할 수 있다.

## 22. 정리

이번 학습에서는 React의 Event 처리와 Router를 활용한 Component 이동 흐름을 정리했다.

핵심 개념은 다음과 같다.

- Event 처리는 사용자의 행동에 반응하는 로직을 작성하는 것이다.
- `onChange`는 input 값이 변경될 때 실행된다.
- `onSubmit`은 form이 제출될 때 실행된다.
- `onClick`은 버튼이나 요소를 클릭할 때 실행된다.
- Event Handler는 이벤트가 발생했을 때 실행되는 함수이다.
- form의 기본 새로고침 동작은 `event.preventDefault()`로 막을 수 있다.
- Validation은 사용자 입력값을 검증하는 과정이다.
- Axios는 백엔드 API와 HTTP 통신할 때 사용할 수 있다.
- API 요청은 비동기 방식이므로 `async`, `await`를 사용할 수 있다.
- 로그인 성공 시 token을 localStorage에 저장할 수 있다.
- React Router DOM은 Component 간 페이지 이동을 도와준다.
- `Route`는 경로와 Component를 연결한다.
- `useNavigate`는 특정 경로로 이동할 때 사용한다.
- `useLocation`은 이동하면서 전달받은 state를 확인할 때 사용한다.
- Welcome Component에서는 로그인 성공 메시지와 로그아웃 버튼을 구성할 수 있다.
- Inline Style은 JSX 안에서 객체 형태로 스타일을 적용하는 방식이다.