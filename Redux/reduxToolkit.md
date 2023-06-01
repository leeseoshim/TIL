# React Redux Toolit

더적은 양의 redux코드를 짤수있게 도와준다.

    npm install @reduxjs/toolkit

<br/>

# store.js

    import {configureStore,createSlice,} from "@reduxjs/toolkit";

    const toDos = createSlice({
        name: "toDosReducer",
        initialState: [],
        reducers: {
            *action을 따로 지정해주지않아도 add, remove로 자동으로 설정된다.
            *새로운 array를 만들지않으면 return을 적지않아도 된다.
            add: (state, action) => {
                state.push({ text: action.payload, id: Date.now() });
            },
           *새로운 array를 만들지않으면 return을 적어야한다.
           ()=>return{} : return 과 {} 사이에 아무 것도 없다면
            return과 {}의 생략이 가능하다.

            remove: (state, action) =>
                state.filter((todo) => todo.id !== action.payload),
        },
    });

    const store = configureStore({ reducer: toDos.reducer });

    *dispatch를 사용하기위해서 export 시켜준다.
    export const { add, remove } = toDos.actions;
    export default store;

<br/>

## 또 다른 reducer 사용 방법

payload에 값이 들어가있기때문에 따로 설정해주지않아도 된다.

    export const addToDo = createAction("add");
    export const deleteToDo = createAction("delete");

    const reducer = createReducer([], {
        [addToDo]: (state, action) => {
            state.push({ text: action.payload, id: Date.now() });
        },
        [deleteToDo]: (state, action) =>
            state.filter((todo) => todo.id !== action.payload),
    });

<br/>

# 연결

    import { useState } from "react";
    import { connect } from "react-redux";
    import ToDo from "./ToDo";
    import { add } from "../store";

    function Home({ toDos, dispatch }) {
        const [text, setText] = useState("");

        const onChange = (e) => {
            setText(e.target.value);
        };
        const onSubmit = (e) => {
            e.preventDefault();
            setText(e.target.value);
            *dispatch로 add에 값을 넣어보낸다.
            dispatch(add(text));
        };

        return (
            <>
                <h1>To Do</h1>
                <form onSubmit={onSubmit}>
                    <input type="text" value={text} onChange={onChange} />
                    <button>추가</button>
                </form>
                <ul>
                *mapStateToProps로 받아온 state값을 가져와 사용한다.
                    {toDos.map((todo) => (
                    <ToDo {...todo.id} key={todo.id} />
                    ))}
                </ul>
            </>
        );
    }

    *redux state에서 home컴포넌트로 전달해 사용한다.
    function mapStateToProps(state, ownProps) {
        return { toDos: state };
    }
    *dispatch를 가져와 사용한다.
    function mapDispatchToProps(dispatch, ownProps) {
        return {
            dispatch,
            // dispathAddTdo: (text) => dispatch(addTodo(text)),
        };
    }

    *connect를 사용해서 Home컴포넌트와 store를 연결한다.
    export default connect(mapStateToProps, mapDispatchToProps)(Home);

    * dispath만 사용할때는 state부분은 null을 넣어준다.
     export default connect(null, mapDispatchToProps)(Home);
