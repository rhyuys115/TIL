# System Structure & Program Execution

<br>

## 컴퓨터 시스템 구조

![컴퓨터 시스템 구조](System Structure & Program Execution.assets/컴퓨터 시스템 구조.png)

 device controller
- 각각의 I/O Device를 통제를 전담하는 작은 CPU역할을 하는 장치
- CPU의 메모리처럼 각각 작업공간을 갖고 있는데 **로컬 버퍼**라고 한다.
- CPU에 비해 매우 느리다.

registers
- CPU 내부의 memory보다 작으면서 정보를 저장하는 공간

mode bit
- CPU에서 실행되는 것이 운영체제인지 사용자 프로그램인지 구분

interrupt line
- I/O device에 직접 접근할 수 없기에 특정 작업이 마무리 되면 이 라인을 통해 연락

timer

- 무한루프의 프로그램이 혼자 CPU를 독점하는 것을 방지

운영체제와 입출력장치를 통해서만 CPU 접근 가능

<br>

## Mode bit

- 사용자 프로그램의 잘못된 수행으로 다른 프로그램 및 운영체제에 피해가 가지 않도록 하기 위한 보호 장치 필요
- mode bit을 통해 하드웨어적으로 두 가지 모드의 operation 지원
  - 1 사용자 모드 : 사용자 프로그램 수행, 0 모니터 모드 : OS 코드 수행
  - 보안을 해칠 수 있는 중요한 명령어는 모니터 모드에서만 수행 가능한 '특권명령'으로 규정
  - Interrupt나 Exception 발생시 하드웨어가 mode bit을 0으로 바꿈
  - 사용자 프로그램에게 CPU를 넘기기 전에 mode bit을 1로 셋팅

<br>

### Timer

- 정해진 시간이 흐른 뒤 운영체제에게 제어권이 넘어가도록 Interrupt를 발생시킴
- 타이머는 매 클럭 틱 때마다 1씩 감소
- 타이머 값이 0이 되면 타이머 인터럽트 발생
- CPU를 특정 프로그램이 독접하는 것으로부터 보호
- 타이머는 time sharing을 구현하기 위해 널리 이용됨

<br>

### Device Controller

- I/O device controller
  - 해당 정보를 