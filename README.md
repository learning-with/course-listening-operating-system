# 운영체제
## 강의 소개
http://kocw.net/home/search/kemView.do?kemId=1046323

이화여자대학교 반효경 교수님 2014년 1학기
## 강의 설명
운영체제는 컴퓨터 하드웨어 바로 위에 설치되는 소프트웨어 계층으로서 모든 컴퓨터 시스템의 필수적인 부분이다. 본 강좌에서는 이와 같은 운영체제의 개념과 역할, 운영체제를 구성하는 각 요소 및 그 알고리즘의 핵심적인 부분에 대해 기초부터 학습한다.

## 목차
### 1. Introduction to Operating Systems
운영체제란 무엇인가, 운영체제의 목적, 운영체제의 분류, 운영체제의 예, 운영체제의 구조

### 2. System Structure & Program Execution
#### 2.1.
컴퓨터 시스템 구조, Mode bit, Timer, Device Controller, 입출력(I/O)의 수행, 동기식 입출력과 비동기식 입출력, 시스템콜(System Call), 인터럽트(Interrupt)
#### 2.2.
컴퓨터 시스템 구조, 인터럽트(Interrupt), 동기식 입출력과 비동기식 입출력, 시스템콜(System Call), DMA(Direct Memory Access), 서로 다른 입출력 명령어, 저장장치 계층 구조, 프로그램의 실행(메모리 load), 커널 주소 공간의 내용, 사용자 프로그램이 사용하는 함수, 프로그램의 실행

### 3. Process
#### 3.1.
프로세스의 개념, 프로세스의 상태(Process State), 프로세스의 개념, 프로세스 상태도, Process Control Block(PCB), 문맥교환(Context Switch), 프로세스를 스케줄링하기 위한 큐, Ready Queue와 다양한 Device Queue, 스케줄러(Scheduler)
#### 3.2.
동기식 입출력과 비동기식 입출력, 프로세스 스케줄링 큐의 모습. Thread
#### 3.3.
Thread, Single and Multithreaded Processes, Benefits of Threads, Inplemetation of Threads

### 4. Process Management
#### 4.1.
프로세스 생성(Process Creation), 프로세스 종료(Process Termination)
#### 4.2.
프로세스 생성(Process Creation), 프로세스와 관련한 시스템콜, 프로세스 간 협력, Message Passing, Interprocess communication, CPU and I/O Bursts in Program Execution, CPU-brust Time의 분포, 프로세스의 특성 분류, CPU Scheduler & Dispatcher

### 5. CPU Scheduling
#### 5.1.
CPU and I/O Bursts in Program Execution, CPU-burst Time의 분포, CPU Scheduler & Dispatcher, Scheduling Algorithms, Scheduling Criteria, FCFS(First-Come First-Served), SJF(Shortest-job-First), Example of Non-Preemptive SJF, Example of Preemptive SJF, 다음 CPU Burst Time의 예측, Exponential Averaging, Priority Scheduling, Round Robin(RR), Example: RR with Time Quantum = 20, Turmaround Time Varies With Time Quantum
#### 5.2.
CPU-burst Time의 분포, Schedulling Algorithms, Round Robin(RR), Multilevel Queue, Multilevel Feedback Queue, Multi-Processor Scheduling, Real-time Scheduling, Example of Non-Preemptive SJF, Thread Scheduling, Algorithm Evaluation, 39:12

### 6. Process Synchoronization
#### 6.1.
데이터의 접근, Race Condition, OS에서의 race condition(3/3), Example of a Race Condition, The Critical-Section Problem, OS에서 race condition(1/3), If you preempt CPU while in kernel mode…, Initial Attempts to Solve Problem, 프로그램적 해결법의 충족조건, Algorithm 1, Algorithm2, Algorithm3(Peterson's Algorithm), Synchronization Hardware, Semaphores
#### 6.2.
Semaphores, Critical Section of n Processes, Block / Wakeup Implementation, Implementation, Two Types of Semaphores, Deadlock and Starvation, Dining-Philosophers Problem
#### 6.3.
Semaphores, Implementation, Classical Problems of Syncronization, Bounded-Buffer Problem, Readers-Writers Problem, Dining-Philosophers Problem, Monitor
#### 6.4.
Semaphores, Monitor, Bounded-Buffer Problem, Dining Philosophers Example

### 7. Deadlocks
#### 7.1.
교착상태(deadlock), The Deadlock Problem, Deadlock 발생의 4가지 조건, Resource-Allocation Graph(자원할당그래프), Deadlock Prevention, Deadlock의 처리 방법, Deadlock Avoidance, Resource Allocation Graph algorithm, Banker's Algorithm, Example of Banker's Algorithm
#### 7.2.
Deadlock의 처리 방법, Deadlock Avoidance, Example of Banker's Algorithm, p1 request(1, 0, 2), Deadlock Detection and Recovery, Deadlock Ignorance

### 8. Memory Management
#### 8.1.
Logical vs. Physical Address, 주소바인딩(Address Binding), Memory-Management Unit(MMU), Dynamic Relocation, Hadware Support for Address Translation, Some Treminologies, Dynamic Loading, Overlays, Swapping, Dynamic Linking, Allocation of Physical Memory, Contiguous Allocation, Paging
#### 8.2.
Paging, Dynamic Relocation, Paging Example, Address Translation Architecture, Implementation of Page Table, Paging Hardware with TLB, Associative Register, Effective Access Time, Two-Level Page Table, Address-Translation Scheme, Two-Level Paging Example
#### 8.3.
Multilevel Paging and Performance, Two-Level Page Table, Valid (v)/ Invalid (i) Bit in a Page Table, Memory Protection, Inverted Page Table, Inverted Page Table Architecture, Shared Page, Shared Pages Example, Segmentation, Segmentation Architecture, Segmentataion Hardware
#### 8.4.
Segmentation, Segmentation Hardware, Segmentation Architecture, Example of Segmetation, Segmentation Architecture(Cont.), Sharing of Segments, Segmentation with Paging, Address Translation Architecture

### 9. Virtual Memory
#### 9.1.
Demand Paging, Memory에 없는 Page의 Page Table, Page Fault, Steps in Handling a Page Fault, Performance of Demand Paging, Free Frame이 없는 경우, Page Replacement, Optimal Algorithm, FIFO(First In First Out) Algorithm, LRU(Least Recently Used) Algorithm, LFU(Least Frequently Used) Algorithm, LRU와 LFU 알고리즘 예제, LRU와 LFU 알고리즘의 구현, 다양한 캐슁 환경
#### 9.2.
다양한 캐슁 환경, LRU와 LFU 알고리즘의 구현, Paging System에서 LRU, LFU 가능한가?, Clock Algorithm, Page Frame의 Allocation, Global vs. Local Replacement, Thrashing, Thrashing Diagram, Working-Set Model, Working-Set Algorithm, PFF(Page-Fault Frequency) Scheme, Page Size의 결정

### 10. File Systems
File and File System, Directory and Logical Disk, open( ), File Protection, File System의 Mounting, Access Methods
#### 10.1. File Systems Implementation 1
Allocation of File Data in Disk, Contiguous Allocation, Linked Allocation, Indexed Allocation, UNIX 파일시스템의 구조, FAT File System, Free-Space Management, Directory Implementation, VFS and NFS, Page Cache and Buffer Cache
#### 10.2. File Systems Implementation 2
Page Cache and Buffer Cache, 프로그램의 실행

### 11. Disk Management and Scheduling
#### 11.1.
Disk Structure, Disk Scheduling, Disk Management, Disk Scheduling Algorithm, FCFS(First Come First Service), SSTF(Shortest Seek Time First), SCAN, C-SCAN, Other Algorithms, Disk-Scheduling Algorithm의 결정
#### 11.2.
Swap-Space Management, RAID
