# CPU 실행모드

- OS 레이어링 : User(Application Program) - Kernel - Device Driver - Device

- 애플리케이션이 커널에 바로 접근하게 되면 문제가 발생할 수 있음, 유저가 손쉽게 시스템과 하드웨어에 영향을 미칠 수 있기 때문
- System Protection을 위해 CPU에는 2가지 이상의 실행 모드가 필요하다.
  - 각각의 모드 별로 권한(Privilege)이 설정됨
  - 실행 모드의 권한에 따라 접근할 수 있는 메모리, 실행 가능한 명령어가 제한됨
  - Hardware의 지원이 필요

## Kernel Mode와 User Mode

### Kernel Mode

- 모든 권한을 가진 실행 모드
- 운영체제가 실행되는 모드
  - 운영체제는 커널 모드에서 하드웨어를 제어한다
- Privilege 명령어 실행 및 레지스터 접근 가능
  - e.g. I/O 장치 제어 명령어 , memory management register - CR3 (CPU 안에 존재)

### User Mode

- Kernel 모드에 비해 낮은 권한의 실행 모드

- 어플리케이션이 실행되는 모드

- Privilege 명령어 실행은 불가능

### 실행 모드 전환 (execution mode)
- CPU의 실행 모드는 시스템 보호가 목적
- User mode에서 실행중인 어플리케이션이 kernel mode의 권한이 필요한 서비스를 받기 위한 방법이 필요
  - e.g. 카카오톡은 유저 모드에서 실행된다. 그런데 친구에게 메시지를 보내기 위해서는 네트워크에 접근해야한다. 즉 커널 모드에서 네트워크 상으로 패킷을 보내주는 함수를 수행해야 한다. 이를 위해 유저 모드에서 커널 모드로의 실행 모드 전환이 필요하다.

