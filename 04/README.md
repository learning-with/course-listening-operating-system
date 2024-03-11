# Process Management
## 프로세스 생성Process Creation
부모 프로세스가 자식 프로세스 생성

프로세스의 트리(계층 구조) 형성

프로세스는 자원을 필요로 함(운영체제로부터 받거나 부모와 공유)

자원의 공유(부모와 자식이 모든 자원을 공유하는 모델, 일부를 공유하는 모델, 전혀 공유하지 않는 모델)

수행Execution(부모와 지식은 공존하며 수행되는 모델, 자식이 종료될 때까지 부모가 기다리는 모델)

주소공간(Address space)
- 자식은 부모의 공간을 복사함
- 자식은 그 공간에 새로운 프로그램을 올림

유닉스의 예
- fork() 시스템 콜이 새로운 프로세스를 생성
  - 부모를 그대로 복사 OS data except PID + binary
  - 주소 공간 할당
- fork 다음에 이어지는 exec() 시스템 콜을 통해 새로운 프로그램을 메모리에 올림

## 프로세스 종료Process Termination
프로세스가 마지막 명령을 수행한 후 운영체제에게 이를 알려줌(exit)
- 자식이 부모에게 output data를 보냄
- 프로세스의 각종 자원들이 운영체제에게 반납됨
  
부모프로세스가 자식의 수행을 종료시킴(about)
- 자식이 할당 자원의 한계치를 넘어섬
- 자식에게 할당된 태스크가 더 이상 필요하지 않음
- 부모가 종료하는 경우
  - 운영체제는 부모 프로세스가 종료하는 경우 자식이 더 이상 수행되도록 두지 않음
  - 단계적인 종료
 
## fork() 시스템 콜
A process is created by the fork() system call

creates a new address space that is a duplicate of the caller

## exec() 시스템 콜
A process can execute a different program by the exec() system call

replaces the memory image of the caller with a new program

## wait() 시스템 콜
프로세스 A가 wait() 시스템 콜을 호출하 커널은 child가 종료될 때까지 프로세스 A를 sleep 시킨다(blocked)

Child process가 종료되면 커널은 프로세스 A를 깨운다(ready)

## exit() 시스템 콜
- 자발적 종료
  - 마지막 statement 수행 후 exit() 시스템 콜을 통해
  - 프로그램에 명시적으로 적어주지 않아도 main 함수가 리턴되는 위치에 컴파일러가 넣어줌
- 비자발적 종료
  - 부모 프로세스가 자식 프로세스를 강제 종료시킴
    - 자식 프로세스가 한계치를 넘어서는 자원 요청
    - 자식에게 할당된 태스크가 더 이상 필요하지 않으
  - 키보드로 kill, break 등을 친 경우
  - 부모가 종료하는 경우
    - 부모 프로세스가 종료하기 전에 자식들이 먼저 종료됨
   
## 프로세스 간 협력
- 독립적 프로세스Independent Process
  - 프로세스는 각자의 주소 공간을 가지고 수행되므로 원칙적으로 하나의 프로세스는 다른 프로세스의 수행에 영향을 미치지 못함
- 협력 프로세스Cooperating Process
  - 프로세스 협력 메커니즘을 통해 하나의 프로세스가 다른 프로세스의 수행에 영향을 미칠 수 있음
- 프로세스 간 협력 메커니즘IPC, Interprocess Communication
  - message passing: 커널을 통해메시지 전달
  - shared memory: 서로 다른 프로세스 간에도 일부 주소 공간을 공유하게 하는 shared memory 메커니즘 
