Learning rate, Overfitting, Regularization
===
## 1. Learning rate
우리는 Machine learning을 통해 학습을 할 때, ```Gradient descent algorithm```을 사용하여 ```cost function```의 최솟값을 찾는다.
```
식 삽입
```
여기서 α값이 ```learning rate```에 해당한다. (일반적으로 0.01로 설정한다.)
* too big -> overshooting
* too small -> too many, mistake

learning rate가 너무 큰 경우에는 ```overshooting```이 발생할 위험이 있다. 반대로 너무 작은 경우에는 너무 오랜 시간이 걸리고 cost function의 최저점을 
잘못 찾는 경우가 발생한다.    

하지만 Learning rate를 잘 설정한 것 같은데도 학습결과가 좋지 않을 때는 데이터 전처리가 필요하다.

### 1.1. Data preprocessing
데이터 전처리에는 크게 두 가지 방식이 있다.
1. Normalization
2. Standardization

```Normalization```의 경우, 분포 중심을 (0, 0)으로, 분포의 값을 0과 1사이 범위 내로 설정하도록 한다.    
```Standardization```의 경우에는 평균, 분산, 표준편자를 이용하여 데이터를 Normalize한다.

## 2. Overfitting
* ```overfitting```은 머신러닝에서 가장 큰 문제 중 하나이다. overfitting은 모델이 training dataset에 너무 적합해진 상태를 말한다.
* 실제로 학습을 해보면, training dataset에서는 결과가 거의 완벽하게 나온다. 하지만 실제 test dataset에서는 오류가 많이 검출된다.

### 2.1. Solution
해결 방법으로는 대표적으로 두 가지가 있다.
1. 더 많은 training dataset을 학습시킨다.
2. ```Regularization```

## 3. Regularization
일반화는 data를 표현하는 모델을 덜 울퉁불퉁하게 만드는 방법이다.
```
식 삽입
```
여기서 λ는 ```regularization strength```이다. 이 값이 0이면 일반화를 하지 않는다는 뜻이고 1에 가까울수록 일반화를 중요하게 생각한다는 뜻이다.    
이 ```regularization```을 통해서 과하게 울퉁불퉁해진 모델 그래프를 좀 더 일반화된 모양으로 펴준다.
