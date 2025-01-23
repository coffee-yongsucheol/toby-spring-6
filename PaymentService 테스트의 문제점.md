
1. 우리가 제어할 수 없는 외부 시스템에 문제가 생기면?
  - 우리가 만들지 않은 서버를 통해서 환율 정보를 받아오는데
  - 서비스가 중단되던지 인터넷이 끊어지던지 이런건 코드를 통제할 수 있는게 아님
  - 제어할 수 없는 문제점이긴함

2. ExRateProvider 가 제공하는 환율 값으로 계산한 것인가?

3. 환율 유효 시간 계산은 정확한 것인가?


##### 테스트의 구성요소

테스트하는 대상이 있다 (SUT) System Under Test

협력자 (COLLABORATOR)


테스트 -> PaymentService -> WebApiExRateProvider

WebApiExRateProvider 를 테스트하고 싶은게 아님 다른 방법으로 테스트 해야함

PaymentService 항상 동일한 결과를 내면서

테스트 실행을 계속 할 수 있는가

제 3의 오브젝트 협력자 콜라보레이터를 반영 되는게 영향을 미칠 수 있다고 하면
Stub이라고 하는 녀석을 만들면 된다

테스트하는 동안만 협력하도록 하면 된다

ExRateProviderStub -> ExRateProvider 처럼 생겼지만 테스트 에서 의도한 어떤 값만 돌려주는 그런 기능만 딱 가지고 있는 테스트용 오브젝트를 만들면 된다.


의존 관계 주입을 사용해서 의존성을 Stub으로 변경시키면 된다.


Stub은 
Imposter 어떤 사람인 것처럼 다른 사람을 속이는 그런 존재 처럼 똑같은 이름을 가지고 있다
Test Double (대역) 이런 말로도 불린다.












