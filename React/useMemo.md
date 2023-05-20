# useMemo

컴포넌트의 상태값이 바뀌면 컴포넌트가 리렌더링되는데 전체가 렌더링되기때문에 원치않는 부분 까지 렌더링되면 추후에 어플리케이션이 느려질수 있다.

그렇기때문에 ReactMemo로 원치않는 부분의 리렌더링을 막을 수 있다.

    fucntion Btn({text="Button", onClick}){
       return <button onclick={onClick}>{text}</button>
    }

    const MemorizedBtn = React.memo(Btn)

    function Parents(){
        const [value,setValue] = React.useState("");
        const changeValue = ()=> setValue("Change the Text");

        return(
            <MemorizedBtn text="sendToChild1" onClick={changeValue}/>
            <MemorizedBtn text="sendToChild2"/>
        )
    }
