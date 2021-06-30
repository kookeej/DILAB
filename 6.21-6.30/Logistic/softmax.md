Softamx Regression
===
## 1. Softmax Regression
* ```multinomial logistic regression```이라고도 한다. 이름으로 볼 수 있듯이 여러개의 분류 중에서 1개를 고르는 다중 클래스 분류 문제이다.
* ```logistic classification```은 이진 분류를 하는 반면에 ```softmax regression```은 3개 이상의 분류에서 1개를 고르는 알고리즘이다.
* 예를 들어 꽃잎 넓이, 꽃잎의 길이, 잎의 잎맥 등으로 품종을 예측하는 데에 사용된다.

### 2. Softmax function
기존 logistic regression과 마찬가지로 ```sigmoid function```을 사용하면, 각각 항목이 정답일 확률이 0 ~ 1 사이의 값으로 나온다.    
예를 들어 3개의 항목이 각각 정답일 확률이 0.8, 0.6, 0.3과 같이 나왔다고 가정하자. 이를 전체 확률이 1이 되도록 바꿔주는 것이 ```softmax function```의 역할이다.    
sigmoid function과 마찬가지로 입력한 데이터를 0 ~ 1 사이의 값으로 변환한다. 그 뒤에 softmax function을 통해 전체의 합이 1이 되도록 ```확률```로 만들어주는 것이다.    
```
S(yi) = 
```
#### 2.1. One-hot Encoding
softmax function을 거쳐 확률로 표현된 항목들을 ```one-hot encoding```을 통해 한 가지 항목만 활성화되도록 만든다. 가장 큰 값이 아닌 다른 값들은 의미가 없는 값이 되도록 만들어주는 것이다. 
확률이 가장 큰 값은 1로 설정하고 나머지는 0으로 만든다. 이렇게 되면 가장 확률이 큰 항목만 활성화가 된다.

### 3. Cross Entropy Cost function
* softmax function에서 cost function은 ```cross entropy```로 정의한다. 
#### 3.1. Cross Entropy
* 예측한 값과 실제값의 차이를 계산한다.
* ```entropy```값이 감소하는 방향으로 찾아나가면 최저값을 찾을 수 있다.
* ```entropy```란, 불확실성에 대한 척도이다. 만약 주머니에 500원만 10개가 들어있다면, 내가 주머니에 손을 넣어 500원을 꺼낼 확률은 1이다.
이 경우 entropy는 0이다. 불확실성이 커질수록 entropy도 커진다.
* Cross Entropy function의 내부구조는 Logistic regression의 내부구조와 유사하다.

```
D(S,L) = -
L = (1/N)
```
