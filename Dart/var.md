# Variable

## var

대체적으로 메소드나 함수내부에서 지역변수를 선언할때는 var를 사용하고,
class안에서는 타입을 지정해준다.

변수의 타입을 구체화하지않아도 자동으로 지정된다.
name이라는 변수의 값을 바꿀때는 같은 타입이여야한다.

    var name = "test";
    name = "hi";

    String name = "test";

<br/>

## Dynamic

타입을 정하지않고, 여러가지 타입이 될 수 있도록 하는 것

    var name;
    dynamic name;

<br/>

## final

재할당 할 수 없다.

    final name = "test";

<br/>

## const

컴파일할 때 값 때 반드시 알고 있어야하는 변수를 정해놓을 때 사용한다.
final과 같이 재할당이 불가능하다.

    const api_key= "test";

<br/>

## null safety

개발자가 null값을 참조 할 수 없도록 하는 것
null값을 참조하게 되면 런타임에러가 뜬다.
런타임에러는 앱을 사용하던 중에 뜨는 에러라는 뜻이다.
그렇기때문에 값이 null이 될수 있음을 명시해준다.

    String? name = "hi";
    name = null;
    *변수 사용전에 null인지 확인
    name?.isNotEmpty;

<br/>

## late

초기 데이터 없이 변수를 선언할수 있게 해준다.
String, var, int, final 등 앞에 써서 사용

    late final String name;
