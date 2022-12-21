# 회원가입 / 로그인 구현

## 1. 파일 구조

  - 로컬 스토리지와 baseURL을 가지는 Axios 생성함수를 utils 폴더에 작성했습니다.
  - email 및 password 의 유효성 검사는 별도로 작성하지 않았습니다.
  - Input 컴포넌트와 버튼 컴포넌트를 작성해 각각 로그인, 회원가입 페이지에 사용하였습니다.

```
└─src
  │  App.css
  │  App.js
  │  index.css
  │  index.js
  │  
  ├─components
  │  ├─Input
  │  │      Input.jsx
  │  │      Input.module.css
  │  │      
  │  ├─SignButton
  │  │      SignButton.jsx
  │  │      SignButton.module.css
  │  │      
  │  └─TodoItem
  │          TodoItem.jsx
  │          TodoItem.module.css
  │          
  ├─pages
  │  ├─Home
  │  │      Home.jsx
  │  │      Home.module.css
  │  │      
  │  ├─SignIn
  │  │      SignIn.jsx
  │  │      
  │  ├─SignUp
  │  │      SignUp.jsx
  │  │      
  │  └─TodoList
  │          TodoList.jsx
  │          TodoList.module.css
  │          
  └─utils
          localStorage.js
          myAxios.js
```
## 로그인 화면

![image](https://user-images.githubusercontent.com/83552466/208837051-0042be9b-014f-40d2-9f3b-cc493d145adb.png)

## 회원가입 화면

![image](https://user-images.githubusercontent.com/83552466/208837157-98622609-8e58-418a-9ac7-6f3a9abe4c06.png)

## 구현 기능

- Assignment1 이메일, 비밀번호 유효성 검사기능

  - [x] 이메일 조건: @ 포함
  - [x] 비밀번호 조건: 8자 이상
  - [x] 입력된 이메일과 비밀번호가 위 조건을 만족할 때만 버튼이 활성화

```js
  const [isActive, setIsActive] = useState(false);

  const handleChange = () => {
    const emailValid = emailRef.current.value.includes("@");
    const passwordValid = passwordRef.current.value.length >= 8;
    emailValid && passwordValid ? setIsActive(true) : setIsActive(false);
    return;
  };
```
요구사항 이상의 유효성 검사는 하지 않았고
onChage핸들러를 할당해서 입력시 유효성 검사 및 활성화 를 수행하도록 했습니다.

