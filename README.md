# React Start!!!!!!
#### 기본 문법 익히기(2021.09.01 ~)

기본 환경 : node.JS

### 1. Settings

  > (1) react 기본 환경 설치 (npx 이용)
  ```
  npx create-react-app //<Project Name>
  ```
  > (2) package.json 
  ```
  "scripts": {
    "start": "react-scripts start", //서버 실행
    "build": "react-scripts build"  //빌드
  },
  ```
  > (3) Git remote push   

<br/>

### 2. Basic Structure

  > /public/index.html //실제 index 전체 문서 틀   
     
  > /src/index.js //ReactDom 을 Rendering 하는 기본 init 개념의 컨트롤러
  ```
  import React from 'react';
  import ReactDOM from 'react-dom';
  import App from './App';

  ReactDOM.render(
    <React.StrictMode>
      <App />    //app.js 의 export 컴포넌트가 들어감
    </React.StrictMode>,
    document.getElementById('root')   //기본 페이지(index.html)의 root(Id) 공간 안, 가상의 Dom 자리를 마련하는 형식  
  );
  ```
  > /src/app.js.  //실제 컴포넌트 구성
  ```
  import React from 'react';

  const App = () => {
    return (
      <div>
        //JSX 영역
      </div>
    );
  };

  export default App;
  ```

