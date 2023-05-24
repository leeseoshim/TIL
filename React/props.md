# Props

컴포넌트 간에 데이터를 주고받을 때 사용한다.

    fucntion Btn({text="Button", onClick}){
       return <button onclick={onClick}>{text}</button>
    }

props로 text를 받지 못 했을 시를 대비해 기본값을 설정할 수 있다.

<br/>

    function Parents(){
        const [value,setValue] = React.useState("");
        const changeValue = ()=> setValue("Change the Text");

        return(
            <Child text="sendToChild1" onClick={changeValue}/>
            <Child text="sendToChild2"/>
        )
    }

<child text="sendToChild1"/> 이 형식은
child({text:"sendToChild1"})로
child함수에 인자를 보내주는 것과 같다.

Child컴포넌트에 넣은 props onCLick은 이벤트리스너가 아니고, props이름일뿐이다. 이름만 같을뿐 절대 이벤트리스너가 아니다!

<br/>
<br/>

# Prop Types

사용법
npm i prop-types

    import PropTypes from "prop-types";

Prop Types을 지정해 놓으면 props시킬 때 잘못된 타입을 보내면 콘솔창에서 경고문구를 받을 수 있다.

    fucntion Btn({text="Button", number}){
       return <button>{text}</button>
    }

    Btn.propTypes = {
        text: PropTypes.string,
        number: PropTypes.number.isRequired,
    }

필수로 보내야하는 데이터가 있다면 뒤에 isRequired를 붙히면된다. 보내지않으면 콘솔창에서 경고문구를 받을 수 있다.
