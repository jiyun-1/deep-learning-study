Layer을 깊이 쌓는 과정에서 문제 발생
Degradation Problem: 더 많은 Layer에도 불구하고, 오히려 적은 Layer의 모델이 더 좋은 성능을 낸다.
-> ResNet: Skip Connection 구조를 통한 Residual Learning 사용


코드 작성 중 막힌 내용
x = 레이어(x) 형태로 출력을 다음층 입력으로 넘겨줘야 연결된다.
두 텐서를 더할 때는  output = keras.layers.Add()([input1, input2]) 

처음에 .numpy()로 변환하지 않아서 gray_images[probe_indices]에서 TypeError가 발생했다.

Encoder에서 
training = False와 trainable = False 의미
- encoder(x, training=False):encoder를 학습모드가 아닌 추론 모드로 계산하라는 의미(BN 고정)
- encoder.trainable = False: encoder의 가중치를 업데이트 하지 말라는 의미
