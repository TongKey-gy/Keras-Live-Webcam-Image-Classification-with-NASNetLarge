# NASNetLarge 기반 웹캠 실시간 이미지 분류 실습 (Keras)

이 저장소는 **TensorFlow/Keras** 프레임워크와 **사전 학습된 딥러닝 모델**을 사용하여 웹캠을 통해 들어오는 이미지를 실시간으로 분류하는 대화형(Interactive) 실습을 담고 있습니다. 이 실습은 Google Colab 환경에서 사용자 상호작용 및 전이 학습(Transfer Learning)의 실제 적용을 보여줍니다.

## 주요 특징:

* **사전 학습 모델 활용:** ImageNet 데이터셋으로 미리 학습된 고성능 이미지 인식 모델인 **NASNetLarge**를 사용하여 모델의 추론(Inference) 능력을 시연합니다.
* **라이브 웹캠 입력:** 사용자 정의 JavaScript 함수를 활용하여 Colab 노트북 환경에서 직접 웹캠에 접근하고 사진을 촬영하는 기능을 구현했습니다.
* **실시간 분류:** 촬영된 이미지를 즉시 전처리한 후, NASNetLarge 모델에 입력하여 대상 이미지를 실시간으로 분류합니다.
* **Top-K 예측:** 모델이 예측한 **가장 높은 확률의 상위 3개** ImageNet 클래스 결과(클래스명, 확률)를 출력합니다.
* **엔드 투 엔드 워크플로우:** 이미지 캡처, 모델 입력 형식에 맞춘 전처리(Resizing, 정규화), 예측 및 결과 해석까지의 전체 과정을 포함합니다.

## 사용 기술:

* **TensorFlow / Keras:** 딥러닝 모델 로딩 및 추론(Inference).
* **IPython.display:** Colab 환경에서 JavaScript 코드 실행 및 이미지 표시.
* **NumPy:** 이미지 데이터를 효율적으로 처리하기 위한 배열 연산.
* **JavaScript:** 웹 브라우저의 웹캠 접근 및 캡처 기능 구현.

## 실행 방법:

이 프로젝트는 Google Colab 환경에서 실행하도록 최적화되어 있습니다.

1.  **Colab에서 노트북을 엽니다.**
2.  **코드 셀을 순차적으로 실행**합니다. 웹캠 접근 권한 요청 팝업이 나타나면 허용합니다.
3.  웹캠 화면이 나타나면, 사진을 찍을 준비가 되었을 때 "Capture" 버튼을 클릭합니다.
4.  모델이 이미지를 분석하고 예측한 상위 3개 분류 결과를 즉시 확인할 수 있습니다.


<실행 결과>
<img width="805" height="626" alt="webcam Result" src="https://github.com/user-attachments/assets/58ca6255-24c4-4be9-8370-29f948d5c627" />
Predicted: [('n04557648', 'water_bottle', np.float32(0.92492133)), ('n03983396', 'pop_bottle', np.float32(0.0054904055)), ('n03825788', 'nipple', np.float32(0.0008485333))]

-상황 : 물병을 webcam에 capture함
-결과 : 이 모델은 water_bottle로 제대로 인식함.
