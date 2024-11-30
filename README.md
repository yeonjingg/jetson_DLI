# jetson_DLI

### 11/7(Thu)
## Introduction and Setup
1. jetpack : Download the Jetson Nano Developer Kit SD Card Image
2. sd memory card formatter, balena etcher로 sd카드 굽기
3. jetson nano module의 구성
![image](https://github.com/user-attachments/assets/2b741da1-8e48-467c-964b-39f86dc71ee3)

![image](https://github.com/user-attachments/assets/c603d0f3-506b-474b-bed3-69573b70f84c)
1) MIPI CSI 카메라 커넥터 옆 또는 배럴 전원 포트 (B01 버전) 뒤에 위치해 있는 J48 2핀 커넥터에 2핀 점퍼를 꽂아줍니다. 점퍼 연결 후 DC 배럴 전원 공급이 활성화됩니다.
2) DC 배럴 잭 전원(5V/4A)을 연결합니다. 젯슨 개발자 키트의 전원이 켜지고 자동으로 부팅됩니다.
3) 개발자 키트의 전원이 켜지는 즉시 마이크로 USB 커넥터 옆에 있는 녹색 LED에 불이 들어옴을 확인할 수 있습니다.


### 11/14(Thu)
## Cameras
![image](https://github.com/user-attachments/assets/db2d72c8-872f-4645-a691-ccf5976cbf32)
USB 커넥터를 젯슨 개발자 키트의 아무 USB 포트에나 연결하면 됩니다.

## Headless Device Mode
![image](https://github.com/user-attachments/assets/d7227abe-5741-471c-9544-5b89a46512ea)

![image](https://github.com/user-attachments/assets/a2738ab3-9b33-4500-aa25-87ec2b6fba62)



### 11/21(Thu)
## Headless Mode
본 과정에서는 "headless"구성을 통해 젯슨 나노 개발자 키트를 실행합니다. 
이 방법은 모니터를 젯슨 나노 개발자 키트에 직접 연결하지 않는 데 나노 키트의 메모리 리소스를 절약하고, 모니터, 키보드 및 마우스와 같은 추가 하드웨어의 필요성을 제거함으로써 추가적인 이점을 제공합니다.
또한 "USB Device Mode"를 사용하여 구성을 더 단순화 할 수 있습니다. 
이 모드에서는 젯슨 나노 개발자 키트가 USB케이블을 통해 컴퓨터에 직접 연결됩니다. 
이렇게 하면 젯슨 나노에서 네트워크 연결이 필요 없을 뿐만 아니라 네트워크의 IP 주소를 지정할 필요도 없습니다. 

1) 프롬프트에 코드 입력
2) 실행
3) 젯슨 나노에서 실행 중인 주피터랩 서버 열기 


## Thumbs Project_Image Classification Project
이 연습 예제의 목표는 라이브 카메라 앞에 있는 수 신호의 의미를 결정하는 이미지 분류 프로젝트를 구축하는 것입니다. ( thumbs-up 또는 thumbs-down)

데이터를 수집하고 데이터를 분류할 수 있도록 모델을 트레이닝하고 thumbs-up 또는 thumbs-down를 올바르게 분류할 때까지 필요한 만큼 모델 테스트와 업데이트함.

1) 노트북 열기: 주피터랩 인터페이스의 classification 폴더로 이동한 다음 classification_interactive.ipynb 노트북을 더블 클릭하여 열기
2) 모든 코드블록 실행하기
3) 초기 데이터를 수집하기
![image](https://github.com/user-attachments/assets/971d362a-2689-468a-9a33-230a8208d100)
![image](https://github.com/user-attachments/assets/de72440a-fe29-4d06-a6ae-87868e616177)

4) 초기 데이터로 훈련하기
![image](https://github.com/user-attachments/assets/d2037619-2879-45b5-9ef5-afd4a83deaac)

5) 실시간으로 데이터 테스트하기
6) 모델 개선하기
7) 모델 저장하기



