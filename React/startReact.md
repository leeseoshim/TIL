# How to use React

1. node.js 다운로드 후 npx커맨드가 실행되는지 확인
2. npx create-react-app 폴더명
   해당 폴더에 만들경우에는 폴더명 대신 .을 적어주면 된다.

<br/>

## 코드가 보여지는 과정

public폴더에 있는 index.html에 id root를 src폴더에 있는 index.js에서 가져와 ReactDom으로 렌더링해준다.
render은 React element를 HTML에 배치해 사용자에게 보여주는 역할을 한다.

import받아온 App컴포넌트를 root아래에 두고 렌더링시키기때문에 APP컴포넌트안에 작업을 해주면 된다.

index.js에서 root에 렌더링 -> index.html에 쌓여 사용자에게 보여짐

<br/>

## 필요한 파일

index.html, index.js와 App.js를 제외하고는 삭제해도 무관하다.

<br/>

## css파일

css파일을 Button.module.css처럼 모튤로 만들어서
import styled from "./Button.module.css" 해당 컴포넌트에 넣어준다.

이렇게 만들게 되면 클래스이름을 랜덤으로 갖게되기때문에 같은 className을 가지게 되어도 다른 컴포넌트와 겹치지않게 사용할수있어서 이름을 일일히 기억하며 다르게 만들필요가 없다.

    <button className={styled.btn}>버튼</button>

개발자모드로 elements를 보면 className가 랜덤으로 만들어진 것을 확인할 수 있다.
