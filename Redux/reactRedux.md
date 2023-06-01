# React Redux

## 사용 방법

redux를 사용할 컴포넌트를 provider로 감싸준뒤 store파일을 import해서 넣어준다.

    import { Provider } from "react-redux";
    import store from "./store";

    const root = ReactDOM.createRoot(document.getElementById("root"));

    root.render(
        <Provider store={store}>
            <App />
        </Provider>
    );

# store.js

상태값을 관리하는 파일을 만들어준다.

    import { createStore } from "redux";

    const ADD = "add";
    const DELETE = "delete";

    export const addTodo = (text) => {
        return {
            type: ADD,
            text,
        };
    };

    export const deleteTodo = (id) => {
        return {
            type: DELETE,
            id: parseInt(id),
        };
    };

    const reducer = (state = [], action) => {
        switch (action.type) {
            case ADD:
                return [{ text: action.text, id: Date.now() }, ...state];
            case DELETE:
                return state.filter((todo) => todo.id !== action.id);
            default:
             return state;
        }
    };

    const store = createStore(reducer);

    export default store;
