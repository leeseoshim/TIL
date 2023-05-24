# useEffect

useState의 값이 바뀔 때 마다 컴포넌트 전체가 렌더링되는데 원할때만 렌더링되도록 만들 수 있다.

1.  지켜볼 값이 없기때문에 컴포넌트가 처음 렌더링 될때 한번만 실행

        useEffect(()=>{console.log("runOnce"),[]});

2.  useState값이 바뀔때마다 렌더링

        useEffect(실행할 코드, [변화를 지켜볼 값])

        여러개도 가능
        useEffect(실행할 코드, [변화를 지켜볼 값1,변화를 지켜볼 값2])

<br/>

3.  element를 true, false로 숨겼다가 보이는 효과를 넣을 때

        function Hello() {
            useEffect(() => {
                console.log("hi");
                *false값으로 바뀌고 element가 없어질 때 보여줌
                strictMode가 켜져있으면 제대로 작동이 안되기때문에 끄고 테스트하는게 좋다.
                return () => console.log("yoyo");
            }, []);
            return <div>hello</div>;
        }

        function App() {
            const [value, setValue] = useState(false);
            const onClick = () => setValue((currentValue) => !currentValue);
            return (
                <div className="App">
                {value ? <Hello /> : null}
                <button onClick={onClick}>버튼</button>
                </div>
            );
        }
