# Vanilla JS Redux

    npm install redux react-redux

javascript의 state를 관리하는 방법
React와는 별개이고, Angular, Vue.js, Vanilla Javascript등 원하는 곳에서 사용가능하다.

- 크롬에서 Redux DevTools 확장프로그램을 다운받으면 Redux 상태관리를 할 수 있다.

<br/>

# createStore

store데이터를 저장하는 곳이고, 사용하기 위해선 reducer가 필요하다.
reducer는 반드시 함수여야하고, 데이터를 수정하는 기능을 한다.

    import { createStore } from "redeux";

    *default값은 undefined
    const reducer = (state) => {
        return state;
    };

    const store = createStore(reducer);

\*default값 설정 방법

    const reducer = (state=0) => {
        return state;
    };

<br/>

# action

reducer에서 사용하는 두번째 argument이다.

action을 사용하기위해서는 dispatch에 메세지를 보내서 사용해야하는데 이때 action은 반드시 object여야하고, key값은 반드시 type이여야한다.
dispatch를 보내면 reducer를 호출한다.

    const reducer = (count = 0, action) => {
        if (action.type === "add") {
            return count + 1;
        } else if (action.type === "minus") {
            return count - 1;
        }
    };

    const countStore = createStore(reducer);

    countStore.dispatch({ type: "add" });
    countStore.dispatch({ type: "add" });
    countStore.dispatch({ type: "minus" });

    console.log(countStore.getState()); //1

\*redux에서는 if문보다는 주로 switch를 사용한다.

    const reducer = (count = 0, action) => {
        switch (action.type) {
            case "add":
                return count + 1;
            case "minus":
                return count - 1;
            default:
                return count;
        }
    };

<br/>

# subscribe

dispatch가 호출되어 변한 store안의 상태값을 알려준다.

    countStore.subscribe(() => {
        countStore.getState();
    });
