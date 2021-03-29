`catched exception을 runtime exception으로 변경하는건 의미가 다릅니다.
catched exception과 runtime exception의 차이를 아시나요?`

..무슨 말인지 모르겠음...

이게 어떤 상황이냐면, 

`private TodoDao() throws ClassNotFoundException {`
이런 게 있었고 이걸 받는 쪽에서 catch를 했는데  

이렇게 하지 말고 TodoDao 내에서 ClassNotFoundException을 감지를 한 다음에 throw new RuntimeException을 하는 걸로 바꿨거든.

무슨.. 의미일까 
