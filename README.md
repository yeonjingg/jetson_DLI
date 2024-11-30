# jetson_DLI

# 11/7(Thu)
## Introduction and Setup
1. jetpack : Download the Jetson Nano Developer Kit SD Card Image
2. sd memory card formatter, balena etcher로 sd카드 굽기
3. jetson nano module의 구성
![image](https://github.com/user-attachments/assets/2b741da1-8e48-467c-964b-39f86dc71ee3)
![image](https://github.com/user-attachments/assets/3d848113-5e5e-4e6d-8e8c-dffc8cd1dae8)

![image](https://github.com/user-attachments/assets/c603d0f3-506b-474b-bed3-69573b70f84c)   
4. MIPI CSI 카메라 커넥터 옆 또는 배럴 전원 포트 (B01 버전) 뒤에 위치해 있는 J48 2핀 커넥터에 2핀 점퍼를 꽂아줍니다. 점퍼 연결 후 DC 배럴 전원 공급이 활성화됩니다.   
5. DC 배럴 잭 전원(5V/4A)을 연결합니다. 젯슨 개발자 키트의 전원이 켜지고 자동으로 부팅됩니다.   
6. 개발자 키트의 전원이 켜지는 즉시 마이크로 USB 커넥터 옆에 있는 녹색 LED에 불이 들어옴을 확인할 수 있습니다.    
7. sd카드를 꼽고 모니터, 키보드, 와이파이 동글, 마우스 usb 커넥터에 연결합니다.   

8. 우분투 설치
![image](https://github.com/user-attachments/assets/b5f9768c-e0f5-4b71-9b83-10cc4eeeadde)
![image](https://github.com/user-attachments/assets/8ab72ebc-3672-4888-af11-a292b74ac441)
![image](https://github.com/user-attachments/assets/69d8f1de-d2e5-42f0-96b9-493f034d0e28)
![image](https://github.com/user-attachments/assets/65c96e17-c0b0-45fb-81ff-50b7625baa03)
9. 한글설정
   아래 링크 참고합니다.   
    https://driz2le.tistory.com/253

# 11/14(Thu)
## Cameras
![image](https://github.com/user-attachments/assets/db2d72c8-872f-4645-a691-ccf5976cbf32)



USB 커넥터를 젯슨 개발자 키트의 아무 USB 포트에나 연결하면 됩니다.

*사진 캡처 및 영상 동작 확인
![image](https://github.com/user-attachments/assets/aaa7a217-1b99-4a56-888e-631fca6fa8f7)


# 11/21(Thu)
## deeplearning
### 1. 딥러닝과 인공신경망 (Artificial Neural Network, ANN)  
딥러닝은 데이터를 분석하고 예측하는 데 사용되는 심층 신경망(Deep Neural Network)을 기반으로 한 기계학습의 하위 분야입니다.  

#### ANN 개념  
- **구조**: 인간 두뇌의 신경망에서 영감을 얻어 개발된 모델.  
- **학습 과정**:  
  - 입력 데이터에 비선형 함수를 적용해 반복적으로 변환하며 학습.  
  - 각 계층의 중간 출력(특징)은 다음 계층의 입력으로 사용됨.  
- **특징**: ANN은 단순 선형 특징부터 복잡한 비선형 특징(모서리, 윤곽 등)을 결합하여 최종적으로 복잡한 객체를 예측함.

---

### 2. 합성곱 신경망 (Convolutional Neural Network, CNN)  
CNN은 이미지와 같은 데이터에서 유용한 정보를 추출하고 예측하는 데 주로 사용됩니다.

#### CNN 구성 요소  
- **입력 계층**: 이미지를 네트워크로 입력.  
- **은닉 계층**: 합성곱 연산 및 풀링 연산으로 특징 추출.  
- **출력 계층**: 특징을 분류기로 전달(일반적으로 로지스틱 회귀).  

#### 합성곱 연산 (Convolution)  
- **작동 원리**:  
  - 입력 데이터(feature map)와 필터(kernel)를 결합하여 새로운 특징 맵 생성.  
  - 필터는 주어진 데이터에서 가장 유의미한 정보를 자동으로 추출함.
  
- **특징 추출 과정**:  
  - 합성곱 계층 → 풀링(max pooling) 계층으로 반복적으로 데이터의 크기와 특징 축소.  
  - 최종적으로 추출된 특징을 출력 계층에서 사용하여 분류.

---

### 3. Residual Network (ResNet)  
ResNet은 딥러닝에서 매우 깊은 신경망의 학습 최적화를 개선한 모델입니다.

#### 특징  
- **Shortcut connections**: 일부 계층을 건너뛰는 연결을 도입.  
- 스킵된 계층의 출력과 shortcut 출력을 합산하여 네트워크의 최적화 효율 증가.  
- 18층(ResNet-18)부터 152층(ResNet-152)까지 다양한 깊이의 구조로 설계.

#### 장점  
- 네트워크의 깊이가 증가하더라도 학습 효율과 정확도를 유지.  
- Jetson Nano와 같은 소형 플랫폼에서 성능과 효율성의 균형을 제공.

---

### 4. 전이학습 (Transfer Learning)  
전이학습은 사전 학습된 모델의 특징을 새로운 작업에 재사용하는 방법입니다.

#### PyTorch ResNet-18 모델  
- **사전 학습**: ImageNet 데이터셋(1000개 클래스)으로 학습된 모델.  
- **특징**: 선, 곡선, 윤곽 등의 기본 특징을 학습했으며, 이를 새로운 분류 작업에 재사용 가능.

#### Jetson Nano에서의 활용  
- 사전 학습된 모델을 기반으로 빠르게 재학습 가능.  
- 전이학습으로 소규모 데이터셋에서도 모델 성능을 향상.

---

### 5. GPU를 활용한 가속화  
딥러닝 모델의 훈련과 추론에는 대규모 연산이 필요하며, GPU는 병렬 처리 성능을 활용해 속도를 대폭 향상합니다.

#### 딥러닝 프레임워크  
- TensorFlow, PyTorch, Caffe 등은 GPU를 지원해 연산을 최적화.  

#### Jetson Nano의 GPU  
- NVIDIA Maxwell GPU(128코어)를 사용하여 저비용 환경에서 딥러닝 및 AI 실험 가능.

---

### 6. 결론  
Jetson Nano는 저비용으로 딥러닝을 실험할 수 있는 플랫폼이며, 사전 학습된 모델(ResNet-18)과 GPU 가속을 통해 효율적인 딥러닝 모델 개발을 지원합니다.  
CNN, ResNet, 전이학습 등의 개념을 이해하고 PyTorch와 같은 프레임워크를 활용하면, 이미지 분류와 같은 복잡한 딥러닝 작업을 효과적으로 수행할 수 있습니다.

## Headless Mode
본 과정에서는 "headless"구성을 통해 젯슨 나노 개발자 키트를 실행합니다. 
이 방법은 모니터를 젯슨 나노 개발자 키트에 직접 연결하지 않는 데 나노 키트의 메모리 리소스를 절약하고, 모니터, 키보드 및 마우스와 같은 추가 하드웨어의 필요성을 제거함으로써 추가적인 이점을 제공합니다.
또한 "USB Device Mode"를 사용하여 구성을 더 단순화 할 수 있습니다. 
이 모드에서는 젯슨 나노 개발자 키트가 USB케이블을 통해 컴퓨터에 직접 연결됩니다. 
이렇게 하면 젯슨 나노에서 네트워크 연결이 필요 없을 뿐만 아니라 네트워크의 IP 주소를 지정할 필요도 없습니다. 

1) 프롬프트에 코드 입력
2) 실행
3) 젯슨 나노에서 실행 중인 주피터랩 서버 열기 
![image](https://github.com/user-attachments/assets/a2738ab3-9b33-4500-aa25-87ec2b6fba62)

## docker와 swap설치 
![image](https://github.com/user-attachments/assets/d7227abe-5741-471c-9544-5b89a46512ea)
1) docker란? 
컨테이너를 통해 소프트웨어를 격리하고 필요한 자원만 사용하도록 하여 메모리를 효율적으로 활용할 수 있게 합니다. 이를 통해 Jetson의 자원 충돌을 방지하고, GPU 가속을 활용한 딥러닝 작업을 안정적으로 수행할 수 있습니다.   
2) swap이란?
Swap 파일은 가상 메모리 공간을 제공합니다. 즉, 물리적 메모리가 부족할 때 하드 디스크나 SSD의 일부를 메모리처럼 사용하여 추가 작업 공간을 확보합니다. 이를 통해 Jetson에서도 RAM 초과로 인한 제한 없이 Jupyter Notebook을 열거나, 동영상 데이터를 처리하는 등 메모리를 많이 사용하는 작업을 수행할 수 있습니다.

## Thumbs Project_Image Classification Project
이 연습 예제의 목표는 라이브 카메라 앞에 있는 수 신호의 의미를 결정하는 이미지 분류 프로젝트를 구축하는 것입니다. ( thumbs-up 또는 thumbs-down)

데이터를 수집하고 데이터를 분류할 수 있도록 모델을 트레이닝하고 thumbs-up 또는 thumbs-down를 올바르게 분류할 때까지 필요한 만큼 모델 테스트와 업데이트함.


1) 노트북 열기: 주피터랩 인터페이스의 classification 폴더로 이동한 다음 classification_interactive.ipynb 노트북을 더블 클릭하여 열기
2) 모든 코드블록 실행하기
   코드 블록의 의미 확인하기.
    *interactive
    *camera : usb/csi 
    *!ls- ltrh/dev/video : video 0

3) 초기 데이터를 수집하기   
![image](https://github.com/user-attachments/assets/971d362a-2689-468a-9a33-230a8208d100)
![image](https://github.com/user-attachments/assets/de72440a-fe29-4d06-a6ae-87868e616177)

4) 초기 데이터로 훈련하기
![image](https://github.com/user-attachments/assets/d2037619-2879-45b5-9ef5-afd4a83deaac)

5) 실시간으로 데이터 테스트하기
6) 모델 개선하기
7) 모델 저장하기

*) 화면이 어떻게 구현된걸까? by 아이파이 위젯   
iPyWidgets(아이파이 위젯)은 Jupyter Notebook에서 인터랙티브 위젯을 생성하여 데이터를 시각화하거나, 모델을 조작하거나, 인터페이스를 생성할 수 있도록 돕는 Python 라이브러리입니다. 이를 활용하면 코드 실행 결과를 동적으로 조작하고 확인할 수 있어 실험 및 데이터 분석 작업에 매우 유용합니다.




