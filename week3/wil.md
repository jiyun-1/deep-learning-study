# CNN 기본 흐름
Input → Convolution → ReLU → Pooling → … → Flatten → FC Layer → Classification
- convolution: 필터를 이동시키면서 이미지 특징 추출 / padding(가장자리 값 추가), stride(이동 간격)
- ReLU: 비선형성 추가
- pooling :일정 영역에서 대표값을 추출하는 것

# output 크기 = floor((N+2P-F)/S)+1

# Dense vs CNN
Dense: 1차원으로 펼친 입력 형태를 갖고, 뉴런 하나가 입력 전체와 연결됨
CNN: 2차원 구조를 유지하는 입력 형태를 갖고, 뉴런 하나가 입력의 일부를 봄. 

# 이동과 회전
- 등변성: 입력이 이동하면 출력도 같은 만큼 이동함 (이동o 회전x)
- 불변성: 입력이 이동해도 출력이 동일함

필터 개수 = feature map의 수 = 채널의 수 -> 다음 층의 입력 채널
