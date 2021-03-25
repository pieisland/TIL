https://www.inflearn.com/questions/7185

`@Transactional(readOnly = true)` 에 대해서.

readOnly = true 안하면 데이터베이스 default 속성을 따라가게 됨.    
그래서 mysql을 사용하면 REPEATABLE_READ level을 택하지만, 
@Transactional(readOnly = true) 하면 READ_UNCOMMITED로 변경되어 성능상의 이점이 있다고 함.

readOnly는 현재 해당 그 트랜잭션 내에서 데이터를 읽기만 할건지 설정하는 것이다.    
db중 read lock, write rock을 따로 쓰는 경우 해당 트랜잭션에 의도치 않게 데이터를 변경하는 일을 막아주고    
하이버네이트를 사용하는 경우 FlushMode를 Manual로 변경해 .... 뭐라는 건지 모르겠다.   

아니 그래서,    
읽기만 하는 거에 transactional을 붙일 필요가 없다는 거임..? readOnly true 하면 phantom read 현상이 발생할 수 있으니까    
문제도 있는 것 같고. 아예 붙이지 말라고?

그럴거면 강의에서는 왜 붙여놨냐 진짜 너무 짜증남..
