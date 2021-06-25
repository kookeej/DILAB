Logistic Classification
===
# 1. Binary classification
 ```Binary classification```은 두 가지로 분류를 하는 알고리즘이다. 예를 들어 메시지를 받았을 때, 이 메시지가 스팸문자인지 아닌지를 판단해서 스팸 문자함으로 보낸다.
 
 ## 1.1. Linear Regression을 사용할 때의 문제점
 위와 같은 상황에서 Linear Regression을 사용할 때 문제가 생긴다.
 1. 값이 추가됨에 따라 결과가 변동된다. 정확도가 떨어지기도 한다.
 2. 예측값이 0/1이 아니라 1보다 크거나 0보다 작게 나올 수도 있다.     

**0~1 사이로 수를 함축시켜주는 함수가 있으면 좋겠다는 아이디어로부터 ```Logistic hypothesis```가 나왔다.**

# 2. Logistic classification
classification algorithm들 중에서도 정확도가 높은 알고리즘이다. 그렇기 때문에 실제 문제들에 바로 적용할 수 있다.    
```neural network```과 ```deep learning```에 있어서 중요한 구성요소이다.

## 2.1. Logistic hypothesis
예측값을 0~1사이로 함축시키고자 하는 아이디어에서 나왔다.    
```sigmoid 함수```는 위의 목적을 충족시켜준다.
