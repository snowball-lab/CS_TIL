# 가상화와 하이퍼바이저

## 가상화

![image](https://user-images.githubusercontent.com/37072010/112490735-fc3d9c00-8dc2-11eb-8fd8-60e3c56cbfbd.png)

- 하드웨어와 OS가 1:1로 존재하는 구조를 바꿈 => 하나의 하드웨어 위에서 여러 OS가 돌아가는 구조
- 이를 위해 하이퍼바이저라는 소프트웨어/레이어를 도입

### 가상화의 장점

| Consolidation                                                | Decoupling                                                   | Isolation                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| - provisioning(여러 OS 지원)을 쉽게 할 수 있다.<br />- 추가적인 하드웨어의 비용을 줄여준다. | SW와 HW 사이의 의존성을 낮춰준다.                            | Guest OS들은 각각 분리되어있다.                              |
| ![image](https://user-images.githubusercontent.com/37072010/112491720-ea102d80-8dc3-11eb-9f39-63009a3cdcff.png) | ![image](https://user-images.githubusercontent.com/37072010/112491751-f4322c00-8dc3-11eb-8211-348a2508f72f.png) | ![image](https://user-images.githubusercontent.com/37072010/112491777-fbf1d080-8dc3-11eb-8372-b7f17fbce980.png) |

## Hypervisor

- 가상화된 컴퓨터 H/W 자원을 제공하기 위한 관리 계층
  - 게스트 OS 와 H/W 사이에 위치함
  - 게스트 OS : hypervisor가 제공하는 가상화된 H/W 자원을 이용하는 운영체제
- 각 게스트 OS 들은 각각 서로 다른 가상 머신 (Virtual Machine)에서 수행되며 서로의 존재를 알지 못 함
  - H/W에 대한 접근은 hypervisor에게 할당 받은 자원에 대해서만 수행
- Hypervisor는 각 게스트 OS 간의 CPU, 메모리 등 시스템 자원을 분배하는 등 최소한의 역할을 수행

### 장점

- 하나의 물리 컴퓨터에서 여러 종류의 게스트 OS 운용이 가능
- 실제의 컴퓨터가 제공하는 것과 다른 형태의 명령어 집합 구조(Instruction Set Architecture)를 제공 
  => 다른 H/W 환경으로 컴파일 된 게스트 OS 및 응용프로그램도 실행 가능

### 단점

- H/W를 직접적으로 사용하는 다른 운영체제에 비해 성능이 떨어짐
- 반가상화(Para-virtualization) 로 성능저하 문제를 해결하려 하지만 높은 기술 수준이 요구됨

