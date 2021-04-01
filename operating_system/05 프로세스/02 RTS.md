# Runtime System (RTS)

- 프로그래밍 언어가 execution model을 정의한다. e.g. C에는 포인터가 있지만 Java에는 없다.
  - RTS가 이 실행 모델을 구현한다.
  - 실행 파일의 Behavior(그것이 메모리에 올라와서 동작하는 모습)는 프로그램에 의해 결정되는 것이 아니다.  RTS가 system, environment로서 그러한 동작을 구현한다.
- RTS : 각 프로그래밍 언어마다 프로그램이 실행되는 환경을 제공하는 특정한 형태의 런타임 시스템, 아래와 같은 문제들을 해결해준다.
  - 애플리케이션 메모리의 레이아웃(Process memory layout)
  - 프로그램이 변수에 접근하는 방식
  - 프로시저 간 매개변수를 전달하는 매커니즘(Parameter passing between procedures)
  - 운영 체제와의 통신
- 일반적으로 런타임 시스템은 스택과 힙을 구축하고 관리하는 책임이 일부 있으며 가비지 컬렉션, 스레드, 그 밖에 해당 언어로 빌드되는 동적 기능들과 같은 기능들을 포함할 수 있다.
- e.g. ART (android runtime), Node.js (javascript), [JRE](https://www.redhat.com/ko/topics/cloud-native-apps/what-is-a-Java-runtime-environment) (java)

- Runtime Environment를 제공하는 방법
  - call main() : RTS가 프로그램을 실행할 때 먼저 main()을 호출한다.
  - Environment variables : HOME, PATH