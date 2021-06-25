Linear Regression Summary
===
# 1. Linear regression의 적용
Linear regression을 적용할 때, 'HCG'를 기억한다. (H: Hypothesis, C: Cost, G: Gradient descent algorithm)
1. Hypothesis
2. Cost
3. Gradient descent algorithm    

**가설(H)을 통해서 cost(W, b)를 최소화하는 W, b의 값을 찾아내는 것을 ```학습```이라고 한다.**    

# 2. Minimize cost - Gradient descent algorithm
cost(W, b) 또는 cost(W)의 그래프 모양을 확인해보면, 밥그릇과 같은 모양을 갖고 있다. 즉, 어느 임의의 지점에서 경사하강 알고리즘을 통해 최저점을 찾더라도
항상 같은 최저점을 찾을 수 있다.    
```Gradient descent algorithm```을 사용해서 경사도(기울기)가 0이 되는 지점을 찾는다.
```
W := W - α(∂/∂W)cost(W, b) when H(X) = XW + b
```
* α는 ```learning rate```다. learning rate는 선택한 임의의 지점에서 어느 정도 크기의 간격으로 이동하며 학습할 것인지를 나타내는 변수다.    
* (∂/∂W)cost(W, b)는 cost(W, b)를 미분한 값이다. 
