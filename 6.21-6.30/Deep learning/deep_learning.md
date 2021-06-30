Deep Learning
===
## 목차
1. [XOR problem ](#1.-xor-problem)
2. [Backpropagation ](#2.-backpropagation)
3. [ReLU ](#3.-relu)
4. [Vanising Gradient ](#4.-vanising-gradient)
5. [Dropout and 앙상블 ](#5.-dropout-and-앙상블)

## 서론
* 딥러닝에는 ```활성화 함수```라는 개념이 존재한다. ```활성화 함수```란, 합친 값이 어떤 기준보다 크다면 1을, 작다면 0을 보내준다.
* Logistic regression들을 여러 개 합쳐놓은 것과 유사한 구조다.
* 활성화 함수의 종류로는 ```sigmoid```, ```tanh```, ```ReLU```, ```Leacky ReLU```, ```maxout```, ```ELU```가 있다.

## 1. XOR problem
XOR problem은 한 개의 logistic regression으로는 해결할 수가 없다. 

## 2. Backpropagation
* ```Backpropagation```은 ```역전파```라고 한다.
* Neural Network의 결과가 잘못된 경우, 역으로 돌아가며 해당 오류에 대한 Weight과 Bias를 수정하는 알고리즘이다.
* 하지만 더 많은 layer를 가진 NN에서는 문제점이 발생한다. layer의 수가 많아지게 되면, 오류의 의미가 점점 작아져 제대로 학습시키기가 어려워진다.

### 2.1. Chain rule 연쇄법칙
f(g(x))로 표현 가능한 복잡한 형태의 수식을 간단하게 미분할 수 있는 방법이다.
```
수식 넣기
```

## 3. ReLU
역전파에서 ```sigmoid```를 사용할 때, 반복적으로 0과 1사이의 값을 곱해주기 때문에 기울기가 소실되는 상황이 발생한다. 이를 ```vanising gradient```라고 한다.
이 문제점을 해결하기 위해 sigmoid 대신에 ```ReLU``` 함수를 사용한다. 내부 layer들에는 거의 ReLU를 사용하고 마지막은 sigmoid 함수를 사용해준다면
정확도는 더 향상된다.
```
f(x) = max(0, x)
//0보다 작으면 0, 0보다 크면 그 값 그대로를 반환한다.
```

## 4. Vanishing Gradient
```vanishing gradient```의 해결방법은 대표적으로 두 가지이다. 하나는 바로 위 처럼 ReLU 함수를 사용하는 것이고, 다른 하나는 초기 Weight값을 잘 설정하는 것이다.
1. ReLU 함수 사용
2. 초기 Weight값 잘 설정하기

### 4.1. Weight값 초기화
만약 ∀ W=0이라면, 역전파시 ```chain rule```에 의해 모든 입력값의 영향이 0이 된다. 이 상태로는 학습이 불가능하다. 따라서 W값을 아무거나 설정하는 것이 아니라
잘 정하는 것이 중요하다. 대표적인 방법으로 ```RBM```이 있다.

### 4.2. RBM
```RBM```은 ```DBN(Deep Belif Network```라고 하는 십층신뢰신경망을 구성하는 기본 요소이다. 
RBM을 여러겹 쌓아서 심층신뢰신경망을 만든다.
인접한 2개의 layer에 적용된다. 먼저 입력값을 사용하여 출력값을 만들어낸 후, 이 결과값을 사용하여 새로운 입력값을 재생성한다. 
입력 layer부터 결과 layer까지 모두 적용시켜서 NN의 Weight값을 설정하면 DBN이 형성된다.   
하지만, RBM의 경우 구현하기가 복잡하다. DBN은 Layer가 많아질수록 구현하기 어려워지기 때문이다. 따라서 학자들은 더 좋은 방법을 고안해냈는데, 대표적으로 
```Xavier Initialization```과 ```He Initialization```이 있다.

## 5. Dropout and 앙상블
* ```Dropout```은 ```overfitting```의 해결방법이다. 학습할 때 임의의 노드들 몇 개를 학습에 참여시키지 않고, 몇 번 따로 학습시킨 뒤, 
마지막 test dataset을 사용할 때는 모든 노드를 사용하여 결과를 확인한다.
* ```앙상블```은 같은 NN모델 여러 개를 만든 후, training dataset에서 가져올 수 있는 data를 넣어서 학습시킨다. 
* 서로 다른 결과들을 하나로 합쳐서 하나의 결론을 만든 뒤에 이것을 Test dataset에 적용시키는 모델이다. 이 앙상블을 사용하면 2~5%가량 성능이 향상된다.
