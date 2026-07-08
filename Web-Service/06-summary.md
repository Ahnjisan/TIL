# HTML, CSS, JavaScript 실습 정리

## 1. 실습 목표

이번 실습의 목표는 HTML, CSS, JavaScript가 각각 어떤 역할을 하는지 직접 확인하는 것이다.

간단한 로그인 화면을 만들면서 다음 내용을 학습했다.

- HTML로 화면 구조 작성
- CSS로 화면 스타일 적용
- JavaScript로 사용자 이벤트 처리
- 외부 CSS 파일 연결
- 외부 JavaScript 파일 연결
- Live Server로 브라우저에서 실행
- 로그인 성공 시 페이지 이동
- 로그인 실패 시 메시지 출력

전체 흐름은 다음과 같다.

```text
HTML 작성
→ CSS 연결
→ JavaScript 연결
→ Live Server 실행
→ 브라우저에서 동작 확인
```

## 2. HTML의 역할

HTML은 웹 페이지의 구조를 담당한다.

로그인 화면에서는 다음과 같은 요소를 HTML로 구성할 수 있다.

- 제목
- 아이디 입력창
- 비밀번호 입력창
- 로그인 버튼
- 메시지 출력 영역

예시는 다음과 같다.

```html
<body>
  <div class="login-container">
    <h2>Login</h2>

    <form id="loginForm">
      <input type="text" id="username" placeholder="Username">
      <input type="password" id="password" placeholder="Password">
      <button type="submit">Login</button>
    </form>

    <p id="message"></p>
  </div>
</body>
```

이 코드에서 `body` 안에 `div`, `h2`, `form`, `input`, `button`, `p` 태그가 중첩되어 있다.

HTML은 태그의 중첩 구조를 가지기 때문에 들여쓰기를 잘 맞추는 것이 중요하다.

## 3. HTML 태그와 속성

HTML은 태그를 사용해 화면 구조를 만든다.

태그는 속성을 가질 수 있다.

예시는 다음과 같다.

```html
<input type="text" id="username" placeholder="Username">
```

각 요소의 의미는 다음과 같다.

| 요소 | 설명 |
|---|---|
| `input` | 입력창을 만드는 태그 |
| `type="text"` | 텍스트 입력창을 의미 |
| `id="username"` | 요소를 식별하기 위한 값 |
| `placeholder="Username"` | 입력 전 안내 문구 |

HTML 태그는 다음과 같은 구조를 가진다.

```text
태그
→ 속성
→ 속성값
```

## 4. Form

`form` 태그는 사용자 입력을 하나의 양식으로 묶는 역할을 한다.

로그인 화면에서는 아이디와 비밀번호 입력창, 로그인 버튼을 하나의 `form` 안에 배치할 수 있다.

```html
<form id="loginForm">
  <input type="text" id="username" placeholder="Username">
  <input type="password" id="password" placeholder="Password">
  <button type="submit">Login</button>
</form>
```

사용자가 로그인 버튼을 클릭하면 `form`의 `submit` 이벤트가 발생한다.

JavaScript에서는 이 `submit` 이벤트를 감지하여 로그인 로직을 처리할 수 있다.

## 5. CSS의 역할

CSS는 HTML로 만든 구조에 스타일을 적용한다.

CSS를 사용하면 다음과 같은 스타일을 지정할 수 있다.

- 배경색
- 글자 색상
- 글자 크기
- 여백
- 정렬
- 입력창 크기
- 버튼 디자인
- 화면 배치

CSS의 기본 구조는 다음과 같다.

```css
선택자 {
  속성: 값;
}
```

예시는 다음과 같다.

```css
body {
  background-color: #f5f5f5;
}

.login-container {
  width: 300px;
  margin: 0 auto;
}
```

CSS는 선택자를 통해 HTML 요소를 찾고, 해당 요소에 스타일을 적용한다.

## 6. CSS 선택자

선택자는 스타일을 적용할 대상을 의미한다.

대표적인 선택자는 다음과 같다.

| 선택자 | 설명 | 예시 |
|---|---|---|
| 태그 선택자 | 특정 태그에 스타일 적용 | `body`, `h2`, `button` |
| 클래스 선택자 | 특정 class 속성을 가진 요소에 스타일 적용 | `.login-container` |
| 아이디 선택자 | 특정 id 속성을 가진 요소에 스타일 적용 | `#loginForm` |

예시는 다음과 같다.

```css
body {
  font-family: Arial, sans-serif;
}

.login-container {
  padding: 20px;
}

#loginForm {
  display: flex;
  flex-direction: column;
}
```

클래스 선택자는 `.`을 사용한다.  
아이디 선택자는 `#`을 사용한다.

## 7. class와 id

HTML 요소에는 `class`와 `id` 속성을 줄 수 있다.

| 속성 | 설명 | 주 사용 목적 |
|---|---|---|
| `class` | 여러 요소에 공통으로 부여할 수 있는 이름 | CSS 스타일 적용 |
| `id` | 하나의 요소를 식별하기 위한 고유한 이름 | JavaScript에서 요소 접근 |

예시는 다음과 같다.

```html
<div class="login-container">
  <form id="loginForm">
  </form>
</div>
```

`class="login-container"`는 CSS에서 `.login-container`로 접근할 수 있다.  
`id="loginForm"`은 JavaScript에서 `document.getElementById("loginForm")`으로 접근할 수 있다.

## 8. 외부 CSS 파일 연결

CSS를 HTML 내부에 직접 작성할 수도 있지만, 보통은 별도의 CSS 파일을 만들고 HTML에서 연결한다.

외부 CSS 파일은 `head` 영역에서 `link` 태그로 연결한다.

```html
<link rel="stylesheet" href="./css/login.css">
```

각 속성의 의미는 다음과 같다.

| 속성 | 설명 |
|---|---|
| `rel="stylesheet"` | 연결할 파일이 스타일시트임을 의미 |
| `href="./css/login.css"` | 연결할 CSS 파일의 경로 |

CSS를 외부 파일로 분리하면 여러 HTML 파일에서 같은 스타일을 재사용할 수 있다.

## 9. JavaScript의 역할

JavaScript는 웹 페이지의 동작을 담당한다.

로그인 화면에서는 다음과 같은 동작을 JavaScript로 처리할 수 있다.

- 로그인 버튼 클릭 감지
- 사용자가 입력한 아이디 가져오기
- 사용자가 입력한 비밀번호 가져오기
- 입력값 검증
- 성공 시 페이지 이동
- 실패 시 오류 메시지 출력

즉, HTML이 구조를 만들고 CSS가 디자인을 담당한다면, JavaScript는 사용자의 행동에 따른 동작을 담당한다.

정리하면 다음과 같다.

```text
HTML → 구조
CSS → 스타일
JavaScript → 동작
```

## 10. 외부 JavaScript 파일 연결

JavaScript도 별도의 파일로 분리하여 관리할 수 있다.

HTML에서 외부 JavaScript 파일을 연결할 때는 `script` 태그를 사용한다.

```html
<script src="./script/login.js"></script>
```

일반적으로 JavaScript 파일은 `body` 태그가 끝나기 직전에 연결한다.

```html
<body>
  ...
  <script src="./script/login.js"></script>
</body>
```

이렇게 작성하면 HTML 요소가 먼저 로드된 뒤 JavaScript가 실행되기 때문에, JavaScript에서 HTML 요소에 접근할 때 오류를 줄일 수 있다.

## 11. 이벤트

이벤트는 사용자가 웹 페이지에서 발생시키는 동작을 의미한다.

대표적인 이벤트는 다음과 같다.

- 버튼 클릭
- 키보드 입력
- 폼 제출
- 마우스 이동
- 페이지 로드

이번 실습에서는 로그인 폼의 `submit` 이벤트를 사용했다.

```javascript
document.getElementById("loginForm").addEventListener("submit", function(event) {
  event.preventDefault();
});
```

위 코드는 `loginForm`이라는 id를 가진 요소에서 submit 이벤트가 발생하면 특정 함수를 실행한다는 의미이다.

`event.preventDefault()`는 폼 제출 시 기본적으로 발생하는 새로고침 동작을 막기 위해 사용한다.

## 12. DOM

DOM은 Document Object Model의 약자이다.

브라우저는 HTML 문서를 읽고, 각 태그를 객체처럼 다룰 수 있는 구조로 만든다.  
JavaScript는 이 DOM을 통해 HTML 요소에 접근하고 값을 가져오거나 변경할 수 있다.

예를 들어 특정 id를 가진 요소에 접근할 때는 다음과 같이 작성한다.

```javascript
const username = document.getElementById("username").value;
const password = document.getElementById("password").value;
```

위 코드는 `username`, `password`라는 id를 가진 입력창의 값을 가져온다.

DOM을 사용하면 JavaScript에서 HTML 요소를 제어할 수 있다.

## 13. 로그인 로직

이번 실습에서는 간단한 로그인 로직을 작성했다.

사용자가 입력한 아이디와 비밀번호가 정해진 값과 일치하면 로그인 성공으로 처리하고, 그렇지 않으면 실패 메시지를 출력한다.

예시는 다음과 같다.

```javascript
document.getElementById("loginForm").addEventListener("submit", function(event) {
  event.preventDefault();

  const username = document.getElementById("username").value;
  const password = document.getElementById("password").value;
  const message = document.getElementById("message");

  if (username === "admin" && password === "1234") {
    window.location.href = "welcome.html";
  } else {
    message.textContent = "아이디 또는 비밀번호가 올바르지 않습니다.";
  }
});
```

전체 흐름은 다음과 같다.

```text
아이디 입력
→ 비밀번호 입력
→ 로그인 버튼 클릭
→ submit 이벤트 발생
→ JavaScript에서 입력값 확인
→ 조건에 따라 성공 또는 실패 처리
```

## 14. 페이지 이동

JavaScript에서는 `window.location.href`를 사용해 다른 페이지로 이동할 수 있다.

```javascript
window.location.href = "welcome.html";
```

위 코드는 현재 페이지에서 `welcome.html`로 이동하라는 의미이다.

이번 실습에서는 아이디가 `admin`, 비밀번호가 `1234`이면 로그인 성공으로 처리하고 `welcome.html`로 이동하도록 구현했다.

흐름은 다음과 같다.

```text
login.html
→ 로그인 정보 입력
→ JavaScript 검증
→ 성공 시 welcome.html 이동
→ 실패 시 메시지 출력
```

## 15. 주석

HTML에서는 주석을 작성할 수 있다.

주석은 브라우저 화면에 표시되지 않지만, 코드 설명을 위해 사용된다.

HTML 주석은 다음과 같이 작성한다.

```html
<!-- CSS 연결 -->
<link rel="stylesheet" href="./css/login.css">
```

주석을 적절히 사용하면 코드의 역할을 이해하기 쉬워진다.

## 16. 코드 작성 시 주의할 점

코드를 작성할 때는 다음 사항을 주의해야 한다.

첫 번째, 들여쓰기를 맞춰야 한다.  
HTML은 태그가 중첩되는 구조이기 때문에 들여쓰기가 정리되어 있어야 구조를 이해하기 쉽다.

두 번째, 대소문자를 주의해야 한다.  
대부분의 프로그래밍 언어와 개발 환경은 대소문자를 구분한다.

세 번째, 파일을 저장해야 한다.  
VS Code에서 파일을 수정한 뒤 저장하지 않으면 변경 내용이 실행 결과에 반영되지 않을 수 있다.

네 번째, 파일 경로를 정확히 작성해야 한다.  
CSS나 JavaScript 파일 경로가 틀리면 스타일이나 동작이 적용되지 않는다.

예시는 다음과 같다.

```html
<link rel="stylesheet" href="./css/login.css">
<script src="./script/login.js"></script>
```

## 17. HTML, CSS, JavaScript를 분리하는 이유

HTML 파일 안에 CSS와 JavaScript를 직접 작성할 수도 있다.

하지만 실제 개발에서는 역할별로 파일을 분리하는 것이 좋다.

| 파일 | 역할 |
|---|---|
| HTML | 화면 구조 |
| CSS | 화면 스타일 |
| JavaScript | 화면 동작 |

분리해서 관리하면 다음과 같은 장점이 있다.

- 코드의 역할이 명확해진다.
- 유지보수가 쉬워진다.
- 스타일과 동작을 재사용할 수 있다.
- 파일 구조를 파악하기 쉽다.
- 협업 시 충돌을 줄일 수 있다.

정리하면 다음과 같다.

```text
HTML → 구조
CSS → 스타일
JavaScript → 동작
```

## 18. 전체 실습 흐름

이번 실습의 전체 흐름은 다음과 같다.

```text
login.html 생성
→ HTML 구조 작성
→ css/login.css 생성
→ CSS 스타일 작성
→ HTML에서 CSS 연결
→ script/login.js 생성
→ JavaScript 이벤트 로직 작성
→ HTML에서 JavaScript 연결
→ Live Server 실행
→ 브라우저에서 결과 확인
```

실습을 통해 HTML, CSS, JavaScript가 하나의 웹 페이지 안에서 어떻게 연결되어 동작하는지 확인했다.

## 19. 정리

이번 학습에서는 HTML, CSS, JavaScript를 이용해 간단한 로그인 화면을 만들었다.

핵심 개념은 다음과 같다.

- HTML은 웹 페이지의 구조를 담당한다.
- CSS는 웹 페이지의 스타일을 담당한다.
- JavaScript는 웹 페이지의 동작을 담당한다.
- HTML 태그는 속성과 속성값을 가질 수 있다.
- CSS는 선택자를 통해 HTML 요소에 스타일을 적용한다.
- class는 CSS 스타일 적용에 자주 사용된다.
- id는 JavaScript에서 특정 요소에 접근할 때 자주 사용된다.
- 외부 CSS와 JavaScript 파일을 연결하면 코드 재사용성과 유지보수성이 좋아진다.
- 이벤트는 사용자가 웹 페이지에서 발생시키는 동작이다.
- DOM을 통해 JavaScript에서 HTML 요소에 접근할 수 있다.
- `window.location.href`를 사용하면 다른 페이지로 이동할 수 있다.