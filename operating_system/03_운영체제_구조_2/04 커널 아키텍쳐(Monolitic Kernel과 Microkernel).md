# 커널 아키텍쳐(Monolitic Kernel과 Microkernel)

- 일반적인 커널의 구조

![image](https://user-images.githubusercontent.com/37072010/112115771-e9796a80-8bfc-11eb-94e1-a5c0d31b4c5b.png)

## Monolithic Kernel

- 커널이 사용자와 **같은 주소 공간**에 위치함
- 주소 공간을 커널 코드와 사용자가 나누어서 사용
- 커널 코드는 한 '덩어리'로 구성됨
  - 커널은 시스템 콜을 통하여 접근

![image](https://user-images.githubusercontent.com/37072010/112116379-93f18d80-8bfd-11eb-8120-9911d02af4da.png)

- 장점
  - 어플리케이션과 모든 커널 서비스가 같은 주소 공간에 위치하기 때문에, 시스템 콜 및 커널 서비스 간의 데이터 전달 시에 오버헤드가 적음
- 단점
  - 모든 서비스 모듈이 하나의 바이너리로 이루어져 있기 때문에 일부분의 수정이 전체에 영향을 미침
  - 각 모듈이 유기적으로 연결되어 있기 때문에 커널 크기가 커질수록 유지 보수가 어려움

## Microkernel

- 커널 서비스를 기능에 따라 **모듈화**하여 **각각 독립된 주소 공간**에서 실행
- 이러한 모듈을 서버라 하며, 서버들은 독립된 프로세스로 구현
- 마이크로 커널은 서버들 간의 통신(IPC), 어플리케이션의 서비스 콜 전달과 같은 단순한 기능만을 제공

<p float="left">
  <img src="https://user-images.githubusercontent.com/37072010/112117230-78d34d80-8bfe-11eb-9a92-82045208a3db.png" width="400" />
  <img src="https://user-images.githubusercontent.com/37072010/112117315-96a0b280-8bfe-11eb-90f3-349670145e23.png" width="400" /> 
</p>

- 장점
  - 각 커널 서비스 서버가 따로 구현되어 있기 때문에 상호 간의 의존성이 낮음
    - monolithic 커널보다 독립적인 개발이 가능
    - 커널의 개발 및 유지 보수가 상대적으로 용이
  - 커널 서비스 서버의 간단한 시작과 종료가 가능
    - 불필요한 서비스의 서버는 종료 => 많은 메모리 및 CPU utilization 확보 가능
  - 이론적으로 microkernel이 monolithic보다 안정적 <= 문제있는 서비스는 서버를 재시작하여 해결
- 단점
  - Monolithic 커널보다 낮은 성능을 보임 <= 독립된 서버들 간의 통신 및 Context Switching

