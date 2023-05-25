# Router

Router는 화면을 전환시켜주기 위해 사용하고,
사용하기위해서는 ReactRouterDom을 install받아야한다.

ReactRouterDom은 컴포넌트들의 모음집이다.
BrowserRouter, Switch, Route 등이 있다.

    npm i react-router-dom@5.3.0

<br/>

    import { BrowserRouter as Router, Switch, Route } from "react-router-dom";

    import Home from "./components/Home";

    function App() {
        return (
            <Router>
                <Switch>
                    <Route path="/">
                    <Home />
                    </Route>
                </Switch>
            </Router>
        );
    }

BrowserRouter는 보통의 웹사이트와 같은 url을 가지고 있다.

반면에 HashRouter를 사용하게되면 url 뒤에 #이 붙기때문에 일반적으로는 Browser Router를 사용한다.

<br/>

## HashRouter를 사용했을 때 url

    http://localhost:3000/#

Switch 는 Route를 찾아 한번에 하나의 Route만 렌더링 하기 위해서 사용한다.

Route는 endpoint를 뜻하고, 유저가 있는 url에따라 설정한 컴포넌트로 화면을 전환시켜준다.
