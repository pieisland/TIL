https://yaboong.github.io/spring/2019/08/29/why-field-injection-is-bad/

constructor based injection을 사용하면 다음과 같은 장점을 가진다.

- 의존 관계 설정이 되지 않을 때는 객체 생성이 불가능하여 NullPointerException을 방지하고
- 의존성 주입이 필요한 필드를 final로 선언함으로써 immutable해진다.
- 순환 참조 시 앱 구동이 실패하게 하여 StackOverflowError를 막아준다.
- 생성자 주입으로 단위테스트 작성이 좋아진다.
