# 딥러닝 실용 사전 (Practical Glossary for Deep Learning)
이론적 설명보다는 실용적인 설명 기반의 딥러닝 사전입니다.

# A

### Affine Layer
* 맥락 : neural network
* 내용 : 일반적으로 그냥 Fully Connected Layer 라고 생각하면 된다.

# G

### Guided Backpropagation
* 맥락 : DeConv를 이용하여 임의의 뉴런의 그래디언트를 시각화하는 과정애서 사용하는 BP의 종류
* 내용 : 일반적인 BP와는 달리 positive influence만 BP에 반영하여 관심 뉴런의 그래디언트를 보다 선명하게 시각화할 수 있다.

# O

### Optimization to Image
* 연관 개념 : Saliency Map을 하는 과정
* 맥락 : 임의의 클래스 점수를 최대화하는 이미지를 시각화하기 위해 해당 클래스의 스코어의 그래디언트만 1로 설정
* 내용 : 일반적인 방식대로 가중치를 최적화하는 것이 아니라, 이미지 자체를 최적해 나가는 과정 (zero image에서 시작 -> 해당 클래스에서 주목하는 이미지를 그려나간다)

# S

### Saliency Map
* 개념 : 이미지의 각 픽셀의 특성을 반영하도록 그린 맵 (또 하나의 이미지) 으로, 원본 이미지를 변형하거나 단순화하여 보다 의미 있거나 분석이 가능한 형태의 이미지 (맵) 으로 만들어 준것.
* 연관 개념 : Optimization to Image
