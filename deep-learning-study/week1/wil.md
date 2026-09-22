keras: 딥러닝 오픈소스 라이브러리

1. 데이터 로드
-data를 train과 test로 split
- train_input.shape 과 dtaype을 통해 28x28 이미지와 uint8 타입으로 구성되어 있음을 확인함

2. 데이터 전처리
- 정규화: 데이터 범위를 0~1 사이로 변환함 
- 평탄화: 2차원 이미지를 1차원 배열로 펼침

3. 모델 설계
- sequential하게 layer 붙임
- 입력층: 784개의 1차원 데이터를 입력 받음
  keras.Input(shape = (784, ))
- 출력층: 10개의 클래스에 대해, softmax 활성화 함수 기반을 통해 확률을 출력함
  keras.layers.Dense(10, activation='softmax')

4. 모델 컴파일: 모델 학습 전, 필요한 환경과 방식 설정
- 손실 함수: Sparse Categorical Cross-Entropy (각 클래스에 대한 예측 확률과 실제 클래스 사이의 차이 측정)
  cf. 회귀 문제 - MSE(평균 제곱 오차), 분류 문제 - Cross Entropy Loss
- 평가 지표: accuracy(정확도)
  cf. 분류 모델을 평가할 때는 주로 accuracy, precision, recall, F1 score 등을 이용

5. 모델 학습
- model.fit()를 통해 5번의 epoch 동안 학습함

6. 모델 평가
- model.evaluate()를 통해 오차와 정확도를 검증함

# 가중치를 구할 때 이미지 한 장의 입력 크기(784)와 데이터의 총 개수(60000)을 헷갈려 했다. 우리 모델에서 가중치는 입력 크기와 출력 크기에 의해 구성되므로 데이터 총 개수는 무관함을 이해하고 파라미터의 구조 원리를 파악할 수 있었다.

# 순전파를 통해 입력에서 모델이 어떻게 예측을 출력하는지 알아볼 수 있었고, 개념으로만 알고 있었던 수학적 기법들이 어느 과정에서, 어떤 식으로 무엇을 위해 쓰이는지 알게 되었다.