Linear Regression
===
# 1. Linear Regression concepts
## 1.1. 회귀분석이란?
 회귀분석이란, 변수 사이의 회귀에 대해서 검정이나 추정을 하는 것을 의미한다. 두 변수 x, y에 대하여 x는 이미 정해져있는 정확한 값이고 x를 통해 y를 추정한다. 예를 들어 공부시간과 성적의 상관관계를 알아내고자 할 때, 많은 (공부시간, 성적) 데이터셋을 학습시키고, 이를 통해 추정하고자 하는 새로운 변수 x를 넣었을 때, 학습된 모델을 토대로 성적(y)값을 도출해낼 수 있다.
 ### 1.1.1. 회귀선
  아래에 두 변수 x와 y사이의 적합한 선에 관한 방정식이 주어져있다. 아래 직선은 x에 대한 y의 회귀선이다.
 ```
 y = a + bx
 ```
 

## 1.2. Linear Regression이란?
 ```Linear Regression```이란, 선형회귀, 또는 직선회귀라고도 한다. 독립변수 X에 대해 결정되는 종속변수 Y를 통해 선형 관계를 모델링한다. 여러 분야에서 선형 모델로 설명할 수 있는 것들이 많기 때문에 널리 사용되고 있다.    
 Linear Regression에는 ```hypothesis```와 ```cost```라는 두 가지 중요한 개념이 있다.

## 1.3. Hypothesis and Cost
### 1.3.1. Hypothesis
원하는 선형함수를 찾기 위해서는 먼저 가설을 세운다. 
```
H(x) = Wx + b
```
위와 같이 하나의 일차방정식으로 직선을 표현한다. 여기서 가장 적합한 W, b의 값을 찾는 것이 목표다.    
가장 적합한  W, b를 구하기 위해서는 cost를 가장 작게 하는  W, b를 찾아야한다. 이 과정을 linear regression 학습이라고 한다. 
### 1.3.2. Cost
```
H(x) - y
```
가설과 실제 y값의 차이를 구한다. 하지만 이렇게 단순히 차를 구하는 것은 부호가 생기기 때문에 좋은 방법은 아니다.
```
(H(x) - y)²
```
위와 같이 제곱을 통해 다 양수로 표현한다.
위 식을 일반화하면 아래와 같다.
```
cost(W, b) = 
```
cost function를 찾아내면 cost를 최소화하는 W, b값을 찾아낼 수 있다.     

# 2. Gradient descent algorithm
* cost function을 최소화하는데 효과적이다.
* 그 외 다양한 최소화 문제에 사용된다.
* 위 알고리즘을 적용시키면  cost function을 최소화하는 변수 W, b값을 구할 수 있다.
* cost(w1, w2, w3 ...)와 같은 함수에도 적용시킬 수 있다.    

cost function 그래프의 아무 곳에서나 시작할 수 있다. 아주 조금식 W와 b의 값을 변경시키며 cost(W, b)를 줄인다.     
어떤 시점에서 시작을 하든지간에 항상 최저점에 도달할 수 있다. 따라서 cost function의 최소값을 찾고 싶을 경우, 기계적으로 Gradient descent algorithm을 적용시켜주면 된다.

그래프의 경사면을 따라 조금씩 옮긴다. 미분을 통해 기울기를 구하고 그 값이 0이 되는 지점이 가장 작은 값이다.

## 2.1. Convex function
실제로 cost(W, b) 그래프를 그려보면 아래와 같이 밥그릇을 엎어놓은 것과 같은 그래프가 생긴다.
![Convex function](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMTAzMzBfOTIg%2FMDAxNjE3MTEyMDI1MTU1.OwlAIuvq4DfiiKhhalIfmqnW7JvGnoPJhUqbqu-U-9og.2q3JvXUiv4RzrLNfA51CDzlxJYp3FAv3tDc1JPIbs4Ug.PNG.sideorder%2Fimage.png&type=sc960_832)    

따라서 위와 3차원 그래프도 어느 지점에서 시작하던지간에 동일한 최저점을 찾을 수 있다.    
    
# 3. Summary
## 3.1. Linear regression 설계를 위해 필요한 3가지
1. Hypothesis
```
H(x) = Wx + b를 통해 W, b를 학습한다.
```
2. Cost function
```
cost(W, b)을 통해 실제값과 예측값을 비교한다. 그래프로 그려보면 밥그릇 모양의 그래프가 나온다.
```
3. Gradient descent algorithm
```
경사하강법을 통해 cost를 최적화하는 (W, b)를 찾는다.
```
