 build에 plugins.. configuration.. 어쩌고 하는게 java 1.8을 쓰기 위한 거라고 한다.   
 pom.xml에 쓰는거 왜 쓰는지도 모르고 막 씀...

사용할 스프링 버전을 properties에 명시해주고 같이 쓰면 된다.

스프링 쓸 거라서 dependency에 org.springframework를 해주고

스프링 jdbc 쓸 거라서 sping-jdbc, spring-tx도 해주고.

mysql 쓸 거라서 mysql-connector-java도 추가해주고.

datasource도 쓸 거라서 commons-dpcp2도 추가해주고.
