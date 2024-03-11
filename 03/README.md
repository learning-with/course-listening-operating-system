# Process
## 프로세스의 개념
Process is a program in execution

프로세스의 context
- CPU 수행 상태를 나타내는 하드웨어 문맥
  - Program Counter
  - 각 종 register
- 프로세스의 주소 공간
  - code, data, stack
- 프로세스 관련 커널 자료 구조
  - PCB(Process Control Block)
  - Kernel stack

## 프로세스의 상태
Running: CPU를 잡고 instruction을 수행중인 상태

Ready: CPU를 기다리는 상태(메모리 등 다른 조건을 모두 만족하고)

Blocked(wait, sleep): CPU를 주어도 당장 instruction을 수행할 수 없는 상태, Process 자신이 요청한 event가 즉시 만족되지 않아 기다리는 상태

Suspended(stopped): 외부적인 이유로 프로세스의 수행이 정지된 상태. 프로세스는 통째로 디스크에 swap out

New: 프로세스가 생성 중인 상태

Terminated: 수행execution이 끝난 상태

## Process Control Block(PCB)
운영체제가 각 프로세스를 관리하기 위해 프로세스당 유지하는 정보
- OS가 관리상 사용하는 정보
  - Process state, Process ID
  - scheduling information, priority
- CPU 수행 관련 하드웨어값
  - Program counter, registers
- 메모리 관련
  - Code, data, stack의 위치 정보
- 파일 관련
  - Open file descriptors
 
## 문맥교환Context Switch
CPU가 한 프로세스에서 다른 프로세스로 넘겨주는 과정

CPU가 다른 프로세스에게 넘어갈 때 운영체제는 다음을 수행
- CPU를 내어주는 프로세스의 상태를 그 프로세스의 PCB에저장
- CPU를 새롭게얻는 프로세스의 상태를 PCB에서 읽어옴

## 프로세스를 스케줄링하기 위한 큐
- Job queue

현재 시스템 내에 있는 모든 프로세스의 집합
- Ready queue
  
현재 메모리 내에 있으면서 CPU를 잡아서 실행되기를 기다리는 프로세스의 집합
- Device queues
  
I/O device의 처리를 기다리는 프로세스의 집합

프로세스들은 각 큐를 오가며 수행됨

## 스케줄러Scheduler
- Long-term scheduler(장기 스케줄러, job scheduler)

시작 프로세스 중 어떤 것들을 ready queue로 보낼지 결정

프로세스에 memory를 주는 문제

degree of Multiprogramming을 제어

time sharing system에는 보통 장기 스케줄러가 없음

- Short-term scheduler(단기 스케줄러, CPU scheduler)

어떤 프로세스를 다음번에 running시킬지 결정

프로세스에 CPU를 주는 문제

millisecond 단위로 충분히 빨라야 함

- Medium-Term scheduler(중기 스케줄러, Swapper)

여유 공간 마련을 위해 프로세스를 통째로 메모리에서 디스크로 쫓아냄

## Thread
A thread(or lightweight process) is a basic unit of CPU utilization

Thread의 구성
- program counter
- register set
- stack space

Thread가 동료 thread와 공유하는 task
- code section
- data section
- OS resources

다중 스레드로 구성된 태스크 구조에서는 하나의 서버 스레드가 blocked(waiting) 상태인 동안에도 동일한 태스크 내의 다른 스레드가 실행(running)되어 빠른 처리 가능

동일한 일을 수행하는 다중 스레드가 협력하여 높은 처리율throughtput과 성능향상 가능

병렬성을 높일 수 있음

## Benefits of Threads
- Responsveness
- Resource Sharing
- Economy
- Utilization of MP Architectures
프로세스에게서 memory를 뺏는 문제

degree of Multiprogramming을 제어

##
