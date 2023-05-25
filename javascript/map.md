# Map

Map은 array의 길이만큼 실행되고, 각 item을 거치면서 retrun에 적은 코드로 값을 바꿔준다.

    const number = ["one","two","three","four"];

    number.map(()=>"hi")
    결과값: ["hi","hi","hi","hi"]

    map((첫번째 인수는 각item, 두번째 인수는 index)=>())
