CNN
===
## 1. CNN이란?
* ```Convolution Neural Network```의 약자이며 ```합성곱 신경망```이라고도 한다.    
* CNN은 우리 눈이 서로 다른 이미지를 볼 대 사용되는 신경세포가 다르다는 사실로부터 착안된 알고리즘이다. 높은 정확도를 가지며 문자 인식, 이미지 인식 등에 
사용된다.
* 어떠한 이미지를 작은 부분들로 나누어 각각에 대한 값을 학습시키는 방법이다.

## 2. CNN의 구성
CNN 알고리즘의 구조는 다음 세 가지로 분류된다.
1. Convolution Layer
2. Pooling Layer
3. Fully Connected Layer    

* CNN에서 Convolution layer와 Pooling layer를 여러번에 걸쳐 사용한 후, 마지막에 Fully connected layer를 사용함으로써 하나의 출력값을 도출한다.    
* 하지만, Convolution layer와 Pooling layer를 너무 많이 사용하게 되면 성능 저하가 발생하기 때문에 ```Dropout```을 사용하여 성능저하를 막는다.

### 2.1. Convolution Layer
CNN은 입력받은 이미지를 작은 부분들로 나누어 각각에 대한 값을 학습한다. 
여기서 "작은 부분"들을 입력받아 ```filter```, ```convolution```연산을 수행하는 것이 
```Convolution layer```이다.   
**NxN -> FxF -> (N-F)/stride + 1 (feature map)**
```
* depth: filter의 개수
* feature map size: (N-F)/stride + 1
```
* 하지만 만약 아무런 처리도 없이 convolution layer를 거친다면feature map의 크기가 점점 작아질 것이고 이는 정보가 소실된다는 뜻이다.
* 따라서 ```padding```을 사용해서 feature map이 작아지는 것을 방지한다.    
```padding```이란, 입력받은 데이터의 테두리에 0을 둘러준다. 정보 소실을 방지할 뿐만 아니라 이미지의 테두리를 구분할 수 있게 된다.

### 2.2. Pooling Layer
Pooling은 쉽게 말하면 Sampling이라고 볼 수 있다. 여러 depth를 갖고 있는 feature map 각각의 depth마다 resize(sampling이라고도 한다.)해준 뒤,
다시 합쳐주는 작업을 수행한다. 
* Max pooling: filter size + stride로 sampling한다. 설정한 filter size만큼의 범위에서 가장 큰 값을 반환한다.

### 2.3. Fully Connected Layer
```convolution layer```와 ```pooling layer```를 거쳐 생성된 결과를 ```Neural network```을 거쳐 ```classification```해주는 layer다. 
여기서 최종적으로 이미지의 결과가 나온다.
