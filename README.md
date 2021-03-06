# 딥러닝 실용 사전 (Practical Glossary for Deep Learning)
이론적 설명보다는 실용적인 설명 기반의 딥러닝 사전입니다.

# A

### Activation Map
* 개념 : 특정 레이어에서 convolution과 activation 이 적용된 결과물을 Activation Volume (또는 feature Volume) 이라고 하는데, 그 중 한장의 slice가 바로 Activation Map. 즉 Map은 Volume의 일부 (한장)
* 예시 : AlexNet의 conv5 레이어의 경우 128 x 13 x 13 의 Activation Volume 중 1개이니까 13 x 13
* 관련 개념 : Activation Volume

### Activation Volume
* 개념 : 특정 레이어에서 convolution과 activation 이 적용된 결과물인 feature Volume. Activation Volume의 한장 한장 (즉 각각의 slice) 은 activation map이라고 한다. 
* 예시 : AlexNet의 conv5 레이어의 경우 128 x 13 x 13
* 관련 개념 : Activation Map

### Adversarial Example (Adversarial Attack)
* 개념 : 어떤 이미지 내의 특정 클래스를 강화하는 방향으로 이미지의 최적화 (Optimiatioin to Image) 를 수행함으로써 해당 이미지의 클래스를 왜곡시키는 것.
* 예시 : 입력값으로 스쿨버스의 이미지를 넣어주고 CNN를 돌리는데 엉뚱한 클래스 (예를 들어 타조) 의 그래디언트만 1로 하고 나머지들을 0으로 설정한 후에 BP를 해 주면 겉보기로는 스쿨버스이지만 타조로 분류하게 된다. 
* 원인 : Neural network가 adversarial attack에 취약한 이유는 태생적인 선형성 (linear nature) 때문 (Ian Goodfellow, 2014) 이다. Deep learning이나 Convolutional Neural Network의 문제가 아니다. 더 나아가 이미지에 국한된 문제도 아니다. 음성 인식 등 Neural Network 를 사용하는 그 어떤 modality에서도 발생한다.

### Affine Layer
* 맥락 : neural network
* 개념 : 일반적으로 그냥 Fully Connected Layer 라고 생각하면 된다.
* 발음 : [어화인]

# C 

### Convolutional Neural Network (CNN)
* 참고 : http://xrds.acm.org/blog/2016/06/convolutional-neural-networks-cnns-illustrated-explanation/


# D

### Deep Dream
* 개념 : Optimization to Image 의 응용인데, Optimization to Image에서는 관심 클래스의 스코어의 그래디언트는 1, 나머지 클래스의 스코어의 그래디언트는 0으로 설정해 주는 반면, 딥드림에서는 스코어의 그래디언트를 activation (ReLU) 로 설정해 줌으로써 boosting 효과를 발생시킨다.

# G

### Guided Backpropagation
* 맥락 : DeConv를 이용하여 임의의 뉴런의 그래디언트를 시각화하는 과정애서 사용하는 BP의 종류
* 개념 : 일반적인 BP와는 달리 positive influence만 BP에 반영하여 관심 뉴런의 그래디언트를 보다 선명하게 시각화할 수 있다.

### Grabcut Segmentation Algorithm
* 맥락 : Visualization
* 개념 : Saliency Map과 결합되어 labeled data 없이도 semantic segmentation을 할 수 있게 도와주는 일종의 segmentation algorighm이나, segmentation 품질은 떨어진다. 

# N

### Neural Style
* 개념 : 콘텐츠와 스타일이 서로 싸우면서 결합된다
    * 콘텐츠 - 해당 콘텐츠 이미지의 모든 레이어로부터 "activation을 추출"
    * 스타일 -해당 스타일 이미지의 모든 레이어로부터 "activation의 그램 매트릭스를 추출""

# O

### Occlusion experiment
* 개념 : 이미지에서 도대체 어떤 픽셀이 classification decision에 영향을 주는 것인지 찾기 위해 masking을 활용하는 방법. 이미지의 부위별로 mask를 씌워가면서 특정 클래스의 확률이 얼마나 올라가거나 떨어지는 지를 heatmap으로 그려줌으로써 이를 눈으로 확인할 수 있다. Saliency Map과 유사한 방식이다. 
* 연관 개념 : Saliency Map

### Optimization to Image
* 연관 개념 : Saliency Map을 하는 과정, Deep Dream, Neural Style 모두 Optimization to Image의 일종
* 맥락 : 임의의 클래스 점수를 최대화하는 이미지를 시각화하기 위해 해당 클래스의 스코어의 그래디언트만 1로 설정하고 나머지 클래스의 스코어의 그래디언트는 0으로 설정
* 개념 : 일반적인 방식대로 가중치를 최적화하는 것이 아니라, 이미지 자체를 최적해 나가는 과정 (zero image에서 시작 -> 해당 클래스에서 주목하는 이미지를 그려나간다)

# S

### Saliency Map
* 개념 : 이미지의 각 픽셀의 특성을 반영하도록 그린 맵 (또 하나의 이미지) 으로, 원본 이미지를 변형하거나 단순화하여 보다 의미 있거나 분석이 가능한 형태의 이미지 (맵) 으로 만들어 준것.
* 응용 : 이미지에서 도대체 어떤 픽셀이 classification decision에 영향을 주는 것인지 찾기 위해 이를 활용한다. Occlusion experiment와 유사한 방식이다. 
* 연관 개념 : Optimization to Image, Deep Dream, Neural Style, Occlusion experiment
