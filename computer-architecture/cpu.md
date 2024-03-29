# CPU (Central Processing Unit, Central/Main Processor)

- 메모리에 저장된 명령어를 읽어 들이고, 해석하고, 실행하는 장치
- 구성요소
  - ALU : CPU 내부 계산 담당
  - 제어장치 : 명령어를 읽어들이고 해석
  - 레지스터 : 임시 저장 장치

## ALU

- 레지스터를 통해 피연산자를, 제어장치로부터 수행할 연산을 알려주는 제어신호를 받아 산술연산, 논리 연산 등의 연산을 수행하여 결과 값(특정 숫자, 특정 문자, 메모리 주소)을 레지스터에 저장
  - CPU가 메모리에 접근하는 속도는 레지스터에 접근하는 속도보다 느리기 때문에 ALU가 연산할 때마다 결과를 메모리에 저장한다면 CPU는 메모리에 자주 접근하게 되고, 이는 프로그램 실행속도를 늦출 수 있음
- ALU는 계산결과와 함께 플래그(연산 결과에 대한 추가적인 정보)를 플래그 레지스터로 내보냄
- 연산을 수행한 결과는 일시적으로 레지스터에 저장
  - CPU가 메모리에 접근하는 속도는 레지스터에 접근하는 속도보다 느림, ALU가 연산할 때마다 결과를 메모리에 저장한다면 CPU가 메모리에 자주 접근하게 되고 이는 CPU가 프로그램 실행속도를 늦출 수 있음

### 대표적인 플래그

- 부호 플래그 : 연산한 결과의 부호
- 제로 플래그 : 연산 결과가 0인지에 대한 여부
- 캐리 플래그 : 연산 결과 올림수나 빌림수가 발생했는 지를 나타냄
- 오버플로우 플래그 : 오버 플로우가 발생했는 지를 나타냄
- 인터럽트 플래그 : 인터럽트가 가능한 지를 나타냄
- 슈퍼바이저 플래그 : 커널 모드로 실행 중인지, 사용자 모드로 실행중인지를 나타냄

## 제어장치

- 제어신호를 내보내고, 명령어를 해석하는 부품
- 컴퓨터 부품들을 관리하고 작동시키기 위한 일종의 전기 신호

### 제어장치가 받아들이는 정보

- 클럭(Clock) 신호 : 클럭 주기에 맞춰 한 레지스터에서 다른 레지스터로 데이터가 이동되거나, ALU에서 연산이 수행되거나 CPU가 메모리에 저장된 명령어를 읽어들이는 것
  - 클럭(Clock) : 컴퓨터의 모든 부품을 움직일 수 있게 한느 시간 단위
- 해석해야하는 명령어 : CPU가 해석해야 할 명령어는 명령어 레지스터에 저장되는데, 제어장치는 이 명령어 레지스터로부터 해석할 명령어를 받아들이고 해석한 뒤, 제어 신호를 발생시켜 컴퓨터 부품들에 수행해야할 내용을 알려줌
- 플래그 레지스터 속 플래그 값
- 제어 버스(시스템 버스 중)로 전달된 제어 신호

### 제어장치가 내보내는 정보

- CPU 내부와 외부(= 제어버스로 제어 신호를 내보낸다)로 제어신호를 보냄
- CPU 외부에 보내는 정보 : 메모리에 전달하는 제어 신호, 입출력 장치에 전달하는 제어 신호
- CPU 내부에 보내는 정보 : ALU에 전달하는 제어 신호(수행할 연산을 지시하기 위함), 레지스터에 전달하는 제어 신호(레지스터 간 데이터를 이동, 레지스터에 저장된 명령어를 해석하기 위함)

## 레지스터

### 대표적인 레지스터 종류

- 프로그램 카운터 : 메모리에서 가져올 명령어의 주소를 저장
- 명령어 레지스터 : 해석할 명령어를 저장
- 메모리 주소 레지스터 : 메모리의 주소를 저장
- 메모리 버퍼 레지스터 : 메모리와 주고받을 데이터를 저장
- 플래그 레지스터 : 연산 결과 혹은 CPU 상태에 대한 부가 정보를 저장
- 스택 포인터 : 스택 최상단의 위치를 저장
- 범용 레지스터 : 데이터와 주소를 모두 저장
- 베이스 레지스터 : 저장된 주소는 기준 주소로서 역할을 함

---

<img src="https://github.com/YooJinRa/sarah-til/blob/main/computer-architecture/images/image-cpu.jpeg?raw=true" alt="cpu" width="700" />
