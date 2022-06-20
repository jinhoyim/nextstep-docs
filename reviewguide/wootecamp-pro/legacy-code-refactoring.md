레거시 코드 리팩터링의 학습 목표는 실제 데이터가 존재하는 레거시를 멀티 모듈로 리팩터링하는 것이다.

- 기술적인 내용보다는 처음 보는 사람도 쉽게 읽을 수 있도록 요구 사항을 정리하였는가?
  - 누락된 요구 사항이 없어야 한다.
- 요구 사항을 기반으로 테스트 코드를 잘 작성하였는가?
  - `@DisplayName` 등을 사용하여 테스트의 의미를 한글로 잘 풀어내야 한다.
  - 무엇을 테스트하고자 하는지 테스트 코드를 통해 잘 드러나야 한다.
  - [테스트를 작성하는 방법](https://blog.kingbbode.com/52)
- Lombok을 사용하지 않는다.
- 도메인 객체가 핵심 비즈니스 로직을 담당하는가?
- 스키마 구조가 변경되었을 때 기존 데이터를 손상하지 않고 Flyway를 통해 안전하게 마이그레이션하였는가?
- 클래스와 클래스 간, 패키지와 패키지 간의 의존성은 단방향인가?
  - 단, JPA의 성능 향상을 위해 양방향으로 할 수 있다.
  - 이벤트를 사용할 수 있지만 필수는 아니며, 데이터의 흐름은 단방향이어야 한다.
- 불변식이 보장되는가?
  - 함께 생성되고 함께 삭제되는 객체들을 함께 묶어라.
  - 불변식을 지켜야 하는 객체들을 함께 묶어라.
  - 그 외는 가능하면 분리하라.
- 멀티 모듈을 적용하는 데 의의가 있다. 컨텍스트 간 독립 모듈로 만드는 것을 권장하지만, 계층 간 독립 모듈로 만들 수도 있다.