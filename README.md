# React Start!!!!!!
#### (2021.09.01 ~)


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

  > /public/index.html   (index 전체 문서 틀)   
     
  > /src/index.js   (ReactDom을 Rendering 하는 기본 init 개념의 컨트롤러)
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
  > /src/app.js  (컴포넌트 구성)
  ```
  (예시1) - 함수형 컴포넌트
  import React from 'react';

  const App = () => {
    return (
      <div>
        //JSX 영역
      </div>
    );
  };

  export default App;  
  
  //
  //
  //  
  
  (예시2) - 클래스형 컴포넌트
  import React, { Component } from 'react';   //React.Component 메소드 정의

  class App extends Component {
    render() {
      return (
        <div>
          //JSX 영역
        </div>
      );
    }
  }

  export default App;
  ```
  > 데이터를 이용하는 방식에는 props와 state가 존재함 (중요도는 State >>>> props)    

<br/>

### 3. Props & State   

##### state와 props의 차이점 [React 공식 커뮤니티 인용](https://ko.reactjs.org/docs/faq-state.html)
props (“properties”의 줄임말) 와 state 는 일반 JavaScript 객체입니다. 두 객체 모두 렌더링 결과물에 영향을 주는 정보를 갖고 있는데, 한 가지 중요한 방식에서 차이가 있습니다. props는 (함수 매개변수처럼) 컴포넌트에 전달되는 반면 state는 (함수 내에 선언된 변수처럼) 컴포넌트 안에서 관리됩니다.
  
  > Props 예시 (함수형)
  
  ```
  import React from "react";
  
  function Food({ favourite }) {
    return <h1>I like {favourite}</h1>;
  }

  function App() {
    return (
      <div>
        <h1>Hello</h1>
        <Potato />
        <Food favourite="kimchi" />
        <Food favourite="ramen" />
        <Food favourite="chukumi" />
      </div>
    );
  }
  ```

<br/>
 > State 예시 (클래스형)
  
  ```
  import React, { Component } from 'react';

  class App extends Component {
    
    //데이터 기본 값 선언
    state = {
      count: 0,
    }
    
    //더하기
    add = () => {
      this.setState(current => ({ count: current.count + 1 }));
    }

    //빼기
    minus = () => {
      this.setState(current => ({ count: current.count - 1 }));
    }
    
    //렌더링
    render() {
      return (
        <div>
          <h1>The number is: {this.state.count}</h1>
          <button onClick={this.add}>Add</button>
          <button onClick={this.minus}>Minus</button>
        </div>
      );
    }
  }
  ```
