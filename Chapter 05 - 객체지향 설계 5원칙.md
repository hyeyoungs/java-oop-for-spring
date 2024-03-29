# 05 객체지향 설계 5원칙
### SRP - 단일 책임 원칙
> 어떤 클래스를 변경해야 하는 이유는 오직 하나뿐이어야 한다.

이를 위해, `각 클래스는 하나의 역할과 책임`을 갖게하라.

ex. 남자 클래스 (남자 클래스에 의존하는 다양한 클래스 있다고 가정) 

→ 남자친구 클래스, 사원 클래스, 아들 클래스, 소대원 클래스로 분리

<br>

### OCP - 개방 폐쇠 원칙
> 소프트웨어 엔티티는 확장에 대해서는 열려 있어야 하지만 변경에 대해서는 닫혀있어야 한다.

자신의 확장에는 열려 있고, 주변의 변화에 대해서는 닫혀 있어야 한다.

이를 위해, `상위 클래스 또는 인터페이스를 중간에 둠`

ex. JDBC 인터페이스

JDBC를 사용하는 클라이언트는 디비를 오라클에서 MySQL로 바꾸더라도 Connection을 설정하는 부분 외에는 따로 수정할 필요가 없다.

<br>

### LSP - 리스코프 치환 원칙
> 서브 타입은 언제나 자신의 기반 타입(base type)으로 교체할 수 있어야 한다.

하위 클래스의 인스턴스는 상위형 객체 참조 변수에 대입해 상위 클래스의 인스턴스 역할을 하는데 문제가 없어야 한다.

- 하위 클래스 is a kind of 상위 클래스 (하위 분류는 상위 분류의 한 종류다.)
- 구현 클래스 is able to 인터페이스 (구현 분류는 인터페이스 할 수 있어야 한다.)

이 2개 문장대로 구현된 프로그램이라면 LSP 잘 지키고 있음

ex. 아버지 춘향이 = new 딸() ❌

ex. 동물 뽀로로 = new 펭귄() ⭕️


<br>

### ISP - 인터페이스 분리 원칙
> 클라이언트는 `자신이 사용하지 않는 메서드에 의존 관계를 맺으면 안된다.`

ex. 남자 클래스 (남자 클래스에 의존하는 다양한 클래스 있다고 가정) 

→ 남자친구 interface, 아들 interface, 사원 interface, 소대원 interface로 분리

SPR와 ISP는 같은 문제(한 클래스가 다양한 책임을 가짐)에 대한 두 가지 해답

인터페이스를 통해 메서드를 외부에 제공할 때는 최소한의 메서드만 제공하자.

상위 클래스는 풍성할수록 좋고, 인터페이스는 작을수록 좋다.

왜? 빈약한 상위 클래스를 이용한 경우 여기저기 형변환이 발생하면서 상속의 혜택을 제대로 누리지 못하고 있기 때문

<br>

### DIP - 의존 역전 원칙
> 고차원 모듈은 저차원 모듈에 의존하면 안된다. 두 모듈 모두 다른 추상화된 것에 의존해야 한다.

구체적인 것이 추상적인 것에 의존해야 한다.

`나보다 변화하기 쉬운 것에 의존하지 마라`

ex. domain layer에서는 infra layer를 모르고 있게 하자.
