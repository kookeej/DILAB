RNN
===
## 1. RNN이란?
### 1.1. 순차적 데이터
* 순차적 데이터(sequence data)란, 음성이나 문장과 같은 연속적인 데이터를 말한다.
* 순차적 데이터는 이전 state의 값이 현재의 state값에 영향을 미친다.    

그렇다면 기존의 ```NN```과 ```CNN```으로 순차적 데이터를 학습할 수 있을까?
### 1.2. 순차적 데이터와 RNN
* ```NN```과 ```CNN```은 1 input, 1 output의 형태이다. 순차적 데이터와 같은 series data에 적용하기는 어렵다. 
* 이 순차적 데이터를 위해서 우리는 ```RNN```을 사용한다.

### 1.3. 수식
RNN을 수식으로 표현하면 아래와 같다.
```
Ht = 
```

* RNN 학습 도중에 발생하는 문제는 LSTM, GRU 중 1개를 사용해서 해결한다.
