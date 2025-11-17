<img width="738" height="416" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/ea11fffc-4b8f-47c2-8111-b372c2d09977" /># 과제#2

# TOP 명령어
+ **top 명령어는 현재 OS의 상태를 나타내주는 CLI 어플리케이션**
+ 메모리 사용량, CPU 사용량 등을 나타내주며 top를 실행하는 동안에는 주기적인 업데이트로 실시간에 근접한 내용을 보여줌
<img width="1280" height="375" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/dce9c969-d112-47a7-bb30-a597d2d375b2" />

### 요약 영역
+ 요약영역은 **전체 프로세스가 OS에 대해서 리소스를 어느정도 차지하고 있는지**를 알려줌
+ 요약 영역에 나타나는 대표적인 값은 시간, 유저, 로드 에버리지(Load Average), 테스크(Tasks), CPU, 메모리(memory)가 있음
<img width="1280" height="159" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/378504fd-a3be-4620-92bb-be5208f4ae84" />

### 시스템 현재 시간, OS가 살아있는 시간, 유저 세션수(System time, uptime and user sessions)
+ 가장 먼저 보이는 숫자가 **시스템의 현재 시간**
+ 다음으로 표시되는 것이 **OS가 얼마나 살아있는지** 나타냄
+ 그리고 다음 나타나는것이 **현재 접속중인 유저 세션 수**
+ 좀 더 자세한 유저세션이 궁금하면 who 명령어를 통해 알 수 있음
<img width="1280" height="74" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/ebc0ff02-324a-40a7-9bd0-f98059eae7ab" />

### 로드 애버리지(Load Average)
+ Tasks는 **현재 프로세스들의 상태를 나태내주는 영역**
+ Total은 전체 프로세스, running은 running 상태인 프로세스, sleeping은 대기상태인 process, stopped는 종료된 프로세스, zombies는 좀비상태인 프로세스의 수를 나타냄

### CPU 사용량
+ **CPU가 어떻게 사용되고 있는지 그 사용율을 보여주는 영역**

|항목|설명|
|--|----|
|**us**|프로세스의 유저 영역에서의 CPU 사용률|
|**sy**|프로세스의 커널 영역에서의 CPU 사용률|
|**ni**|프로세스의 우선순위(priority) 설정에 사용하는 CPU 사용률|
|**id**|사용하고 있지 않는 비율|
|**wa**|IO가 완료될때까지 기다리고 있는 CPU 비율|
|**hi**|하드웨어 인터럽트에 사용되는 CPU 사용률|
|**si**|소프트웨어 인터럽트에 사용되는 CPU 사용률|
|**st**|CPU를 VM에서 사용하여 대기하는 CPU 비율|

### 메모리 사용량
|항목|설명|
|--|----|
|**total**|총 메모리 양|
|**free**|사용 가능한 메모리 양|
|**used**|사용중인 메모리 양|
+ **buff/cache**에서 **buff는 buffers의 약자**, 이 값은 **커널 버퍼에서 사용되는 메모리**를 뜻함
+ **cache는 Disk의 페이지 캐시**를 말함. 즉, **buff/cache는 IO와 관련되어 사용되는 버퍼에 사용되는 메모리**
  
### 디테일 영역
<img width="1280" height="230" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/ecc6ade8-c54f-4afb-81cf-aedd92945baf" />

|항목|설명|
|--|----|
|**PID**|PID는 프로세스 ID이며 프로세스를 구분하기 위한 겹치지않는 고유한 값|
|**USER**|해당 프로세스를 실행한 USER 이름 또는 효과를 받는 USER의 이름|
|**PR**|커널에 의해서 스케줄링되는 우선순위|
|**NI**|PR에 영향을 주는 nice라는 값|
|**VIRT**|프로세스가 소비하고 있는 총 메모리|
|**RES**|RAM에서 사용중인 메모리의 크기|
|**SHR**|다른 프로세스와의 공유메모리(Shared Memory)|
|**%MEM**|RAM에서 RES가 차지하는 비율|
|**S**|프로세스의 현재 상태|
|**TIME+**|프로세스가 사용한 토탈 CPU 시간|
|**COMMAND**|해당 프로세스를 실행한 커맨드|

### 주요 단축키
|항목|설명|
|--|----|
|**Q**|top 종료|
|**P**|CPU 사용량 기준 정렬|
|**M**|메모리 사용량 기준 정렬|
|**K**|프로세스 종료( kill )|
|**H**|도움말 표시|

# PS 명령어
+ ps 명령어는 Process Status의 줄임말로 말 그대로 프로세스 상태 등을 확인 할 수 있음
+ $ps [option]
+ ps 명령을 사용하면 현재 실행중인 프로세스들과 상태를 출력
+ ps 명령어는 스냅샷으로 명령어를 입력한 시점을 보여주기 때문에, 실시간으로 프로세스 정보를 보고 싶다면 top 명령어를 사용하면 됨
+ ps 명령어는 UNIX, BSD, GNU 환경에 따라 결과가 다르고 표기법에도 차이가 있음. UNIX 계열은 dash("-")를 사용하고, BSD 계열은 dash를 사용하지 않음. GNU 계열은 두 개의 dash("--")를 사용함
<img width="531" height="396" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/e1258fcb-e59c-4464-a71b-ec7a1656b2c3" />

### 자주 사용하는 옵션
|항목|설명|
|--|----|
|**-e**|실행중인 모든 프로세스를 출력 (-A와 동일한 옵션)|
|**-f**|풀-포맷으로 리스트를 보여준다. UID, PID, PPID 등을 포함해서 출력|
|**-l**|-f 옵션보다 더 자세하게 출력|
|**-a**|세션 리더와 터미널에 연관되어있지 않은 프로세스들을 제외한 모든 프로세스를 출력|
|**a(BSD 계열)**|터미널과 연관되어 있는 프로세스만 출력|
|**-u**|-u [userlist] 와 같이 사용하며, 특정 유저의 프로세스 정보를 출력, 유저를 지정하지 않으면 현재 사용자를 기준|
|**u(BSD 계열)**|프로세스의 소유자를 기준으로 출력|
|**x(BSD 계열)**|a 옵션과 결합하여 모든 프로세스를 출력|

### 예시
1. ps -ef
+ ps -ef 명령어를 사용하면 실행중인 모든 프로세스를 풀 포맷으로 출력
<img width="738" height="416" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/877897cc-20d3-4f18-a723-9c48f18f6e4e" />

|항목|설명|
|--|----|
|**UID**|프로세스를 실행한 User ID|
|**PID**|프로세스 ID (Process ID)|
|**PPID**|프로세스의 부모 프로세스 ID (Parent Process ID)|
|**C**|CPU 사용량(%)|
|**STIME**|프로세스 시작 시간 (Start TIME)|
|**TTY**|프로세스가 실행된 터미널의 종류와 번호|
|**TIME**|프로세스에 의해 사용된 CPU 시간|
|**CMD**|실행된 프로세스의 이름 또는 실행된 명령|

2. ps aux
+ BSD 문법으로 모든 프로세스를 출력하고 싶다면 ps aux 명령어를 사용하면 됨
+ ps -ef 와 차이점은 출력 형식이 다름
<img width="735" height="416" alt="img1 daumcdn" src="https://github.com/user-attachments/assets/f95f51ce-f855-4c79-95e0-5a6fa4cdd53e" />

|항목|설명|
|--|----|
|**USER**|프로세스 소유자의 이름|
|**PID**|프로세스 ID|
|**%CPU**|CPU 사용 비율|
|**%MEM**|메모리 사용 비율|
|**VSZ**|페이지 또는 K단위의 가상메모리 사용량|
|**RSS**|실제 메모리 사용량|
|**TTY**|프로세스와 연결된 터미널|
|**STAT**|현태 프로세스의 상태 코드|
|**START**|프로세스가 실행된 시간|
|**TIME**|총 CPU 사용 시간|
|**COMMNAND**|프로세스의 실행 명령|
