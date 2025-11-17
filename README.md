# 과제#2

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
+ ps 명령어는 Process Status의 줄임말로 말 그대로 **프로세스 상태 등을 확인** 할 수 있음
+ $ps [option]
+ **ps 명령을 사용하면 현재 실행중인 프로세스들과 상태를 출력**
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
1. **ps -ef**
+ ps -ef 명령어를 사용하면 **실행중인 모든 프로세스를 풀 포맷으로 출력**
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

2. **ps aux**
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

# JOBS 명령어
+ **현재 세션에서 실행 중이거나 중단된 작업 목록을 출력**
+ **jobs [옵션]**

|항목|설명|
|--|----|
|**-l**|각 작업의 프로세스 ID(PID)도 함께 출력|
|**-p**|각 작업의 프로세스 ID만 출력|
|**-n**|가장 최근에 상태가 변경된 작업만 출력|
|**-n**|실행 중(Running)인 작업만 출력|
|**-s**|일시중지된 작업만 출력|

### 예시
1. ping 명령어를 백그라운드로 실행한 뒤, jobs 명령어를 사용해 상태를 확인하는 과정
<img width="596" height="136" alt="image" src="https://github.com/user-attachments/assets/f5c96321-3b33-46d2-94b1-739301018d54" />
+ ping 명령어가 백그라운드에서 실행되며, 작업 번호는 1번, 프로세스 ID는 12345이다. jobs 명령어를 입력하면, 현재 실행 중인 작업 목록이 표시됨

2. 다른 명령어를 실행하고, 중간에 일시 중지한 후 작업 목록을 다시 확인
<img width="595" height="181" alt="image" src="https://github.com/user-attachments/assets/7bc7c9b3-b4e8-4675-a962-1e35835039d9" />
+ Ctrl + Z로 sleep 명령어를 일시 중지. 이때 jobs 명령어를 사용하면 두 개의 작업이 표시됨. 첫 번째 작업은 ping 명령어로 Running(실행 중) 상태이며, 두 번째 작업은 sleep 명령어로 Stopped(중지) 상태

### 작업 제어 관련 명령어
|항목|설명|
|--|----|
|**fg**|백그라운드 또는 일시 중지된 작업을 포그라운드로 전환|
|**bg**|일시 중지된 작업을 백그라운드에서 다시 실행|
|**kill**|특정 작업을 종료특정 작업을 종료|

# KILL 명령어
+ **프로세스를 종료할 때 사용하는 리눅스 명령어**
+ **주로 프로세스 ID(PID)를 이용**하여 프로세스를 식별한 후 종료를 시도하며, **시그널(signal)을 이용**해 다양한 방식으로 종료를 처리할 수 있음
+ **kill [옵션] PID**
+ PID는 **프로세스 ID**로, **종료할 프로세스를 식별하는 숫자**
+ 옵션을 통해 특정한 시그널을 보낼 수 있으며, **기본적으로 SIGTERM(15번 시그널)이 사용**

### 주요 시그널
|항목|설명|
|--|----|
|**SIGTERM(15)**|프로세스에게 정상적으로 종료하도록 요청|
|**SIGKILL(9)**|: 즉시 프로세스를 강제 종료. 프로세스가 응답하지 않거나 종료되지 않을 때 사용|
|**SIGHUP(1)**|프로세스를 재시작하거나 종료하는 데 사용|

### 예시
1. ps 명령어로 프로세스 확인
+ ps 명령어로 프로세스를 확인하고 PID를 얻을 수 있음
<img width="593" height="156" alt="image" src="https://github.com/user-attachments/assets/20f18387-5461-4580-a4dc-7f91187546d8" />

+ python3 프로세스의 PID는 5678이다.

2. SIGTERM으로 프로세스 종료
<img width="595" height="61" alt="image" src="https://github.com/user-attachments/assets/1ac4cf5a-3a65-4e38-9045-1162619f4874" />

+ 5678 PID를 가진 python3 프로세스에게 SIGTERM(15) 시그널을 보내 정상 종료를 요청
+ 정상 종료하도록 유도하지만, 프로세스가 이를 무시하거나 응답하지 않을 수 있음

3. SIGKILL로 강제 종료
<img width="593" height="59" alt="image" src="https://github.com/user-attachments/assets/dd040a7d-b96d-492d-b2f5-e490fc8ad84f" />

+ SIGKILL(9) 시그널을 보내 python3 프로세스를 즉시 강제 종료
+ 프로세스가 응답하지 않을 때 유용하며, 해당 프로세스는 강제로 메모리에서 제거

4. SIGHUP으로 프로세스 재시작
<img width="591" height="60" alt="image" src="https://github.com/user-attachments/assets/7ecb30dd-f943-4f87-b0cc-c38b1d0ca93b" />

+ SIGHUP(1) 시그널은 bash 셸을 다시 로드하거나 재시작하도록 유도하는 데 사용
+ 셸이나 데몬 프로세스에 주로 사용되며, 설정 파일을 다시 읽어오는 등의 역할

5. 모든 프로세스 종료
<img width="594" height="60" alt="image" src="https://github.com/user-attachments/assets/3780de3d-8670-4166-8790-39985bc774c2" />

+ 모든 프로세스를 종료하는 것은 PID 1을 제외한 프로세스에 사용될 수 있으며, 프로세스 그룹을 종료하거나 사용자의 모든 프로세스를 종료하는 데 유용
+ 현재 로그인한 사용자의 모든 프로세스를 종료합니다. 매우 위험한 명령이므로 신중하게 사용

6. 프로세스 그룹 종료
<img width="594" height="60" alt="image" src="https://github.com/user-attachments/assets/80667c0f-2344-4805-9224-32885979e385" />

+ 1234와 같은 음수 PID는 해당 프로세스 그룹에 있는 모든 프로세스에 시그널을 보냄
+ 이 경우 1234 PID가 속한 프로세스 그룹 전체가 종료

##### 프로세스 강제 종료 주의 사항
+ SIGKILL(9) 시그널은 프로세스를 강제 종료하기 때문에, 데이터 손실이나 파일 손상이 발생할 수 있음
+ 항상 SIGTERM(15) 시그널로 먼저 프로세스를 종료하고, 응답이 없는 경우에만 SIGKILL을 사용하는 것이 좋음
