# Process

<br>

## 프로세스의 개념

프로세스의 문맥

- CPU 수행 상태를 나타내는 하드웨어 문맥
  - Program Counter
  - 각종 register
- 프로세스의 주소 공간
  - code, data, stack
- 프로세스 관련 커널 자료 구조
  - PCB (Process Control Block)
  - Kernel stack

<img src="C:\Users\YS Rhyu\TIL\운영체제\.assets\프로세스의 개념.png" alt="프로세스의 개념" style="zoom:50%;" />

<br>

## 프로세스의 상태

프로세스는 상태가 변경되며 수행된다

- Running : CPU를 잡고 instruction을 수행중인 상태
- Ready : CPU를 기다리는 상태(메모리 등 다른 조건을 모두 만족하고)
- Blocked(wait,sleep)
  - CPU를 주어도 당장 instruction을 수행할 수 없는 상태
  - Process 자신이 요청한 event(예:I/O)가 즉시 만족되지 않아 이를 기다리는 상태
  - ex) 디스크에서 file을 읽어와야 하는 경우
- New : 프로세스가 생성중인 상태
- Terminated : 수행(execution)이 끝난 상태

<img src="C:\Users\YS Rhyu\TIL\운영체제\.assets\프로세스의 상태2.png" alt="프로세스의 상태2" style="zoom:33%;" />

<br>

<img src="C:\Users\YS Rhyu\TIL\운영체제\.assets\프로세스 상태도.png" alt="프로세스 상태도" style="zoom:33%;" />

<br>

### Process Control Block(PCB)

운영체제가 각 프로세스를 관리하기 위해 프로세스당 유지하는 정보

다음의 구성요소를 가진다(구조체로 유지)

1. OS가 관리상사용하는 정보
   - Process state, Process ID, scheduling information, priority
2. CPU 수행 관련 하드웨어 값
   - Program counter, registers
3. 메모리 관련
   - Code, data, stack의 위치 정보
4. 파일 관련
   - Open file descriptors

<img src="C:\Users\YS Rhyu\TIL\운영체제\.assets\PCB.png" alt="PCB" style="zoom:33%;" />

<br>

## 문맥 교환(Context Switch)

- CPU를 한 프로세스에서 다른 프로세스로 넘겨주는 과정
- CPU가 다른 프로세스에게 넘어갈 때 운영체제는 다음을 수행
  - CPU를 내어지눈 프로세스의 상태를 그 프로세스의 PCB에 저장
  - CPU를 새롭게 얻는 프로세스의 상태를 PCB에서 읽어옴

<img src="C:\Users\YS Rhyu\TIL\운영체제\.assets\문맥 교환.png" alt="문맥 교환" style="zoom:50%;" />

-  System call이나 Interrupt 발생 시 반드시 context switch가 일어나는 것은 아니다.

<img src="C:\Users\YS Rhyu\TIL\운영체제\.assets\문맥 교환2.png" alt="문맥 교환2" style="zoom:50%;" />

- (1)의 경우에도 CPU 수행 정보 등 context의 일부를 PCB에 save해야 하지만 문맥교환을 하는 (2)의 경우 그 부담이 훨씬 큼 (eg.cache memory flush)



