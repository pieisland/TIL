21.03.18.

메소드에 대한거라면 메소드 주석을 사용하는 게 어떻겠냐고 하신 리뷰를 봤다.   
메소드 주석이라 치니까 딱 맞게 나오는 건 없었는데, 이거인 것 같아서 남겨본다.  

https://stackoverflow.com/questions/29815636/and-in-java-comments   
https://velog.io/@foeverna/Java33JavaDocs%EC%A3%BC%EC%84%9D

## javadoc 
```
/**
*
*
*/
```

javadoc 도구에 의해 생성되는 코드에 대한 공식 api를 작성할 때 사용한다.
라고 하지만.. 그게 무슨 말인지 모르겠네요.
그냥 메소드에 대한 설명을 할 때 쓴다고 해도 될 것 같은데.

몇 가지 일반적 요소가 있는데.
@param : 어떤 매개변수가 메소드에 전달되고 어떤 값을 가질 것으로 예상되는지
@return: 메서드가 반환 할 결과를 나타낼 때.
@throws: 특정 입력의 경우 메서드에서 예외 또는 오류가 발생함을 나타낼 때.
@since: 이 클래스나 함수를 사용할 수 있는 가장 초기 java 버전을 나타낼 때.

---------------------------

## 블록(여러 줄) 주석.
```
/*
*
*/
```

주석에 여러 줄 넣을 때 쓴다.
이 형식은 별로 권장안한다고 한다.
..?
그래서 그냥 javadoc 쓰라고 하는 듯.
