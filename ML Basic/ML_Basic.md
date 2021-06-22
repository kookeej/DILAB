Machine Learning Basic concepts
===
## Machine Learning이란?
* 머신러닝(Machine learning)이란, 사람이 일일이 코딩하지 않고 데이터를 통해 스스로 학습하여 실행할 수 있도록 하는 연구 분야이다.
* 컴퓨터를 인간처럼 학습시킴으로써 사람이 일일이 프로그래밍으로 구현할 필요 없이 스스로 새로운 규칙을
 구현하거나, 명확하게 구분할 수 없는 지식(no explicit knowledge)를 구현해야할 때 유용하다. 

## ML의 두 가지 학습 방법
1. ```Supervised learning```
2. ```Unsupervised learning```

## Supervised learning
* Learn with labelled examples - trainig set
* 라벨링된 데이터셋으로 학습한다.

### Training dataset
X   |  Y    
5,6 |  3    
3,4 |  2    
1,2 |  1    
이 dataset을 학습하여 모델을 생성한다.

X_test = [6,5] => Y=3 도출!

### Supervised learning type
1. Regression   
```
과거 데이터로부터 예측한다.
```
2. Binary classification   
```
Pass/Nonpass와 같이 2가지 유형으로 분류한다.
```
3. Multi-level classification   
```
학점 등급(A,B,C,D..)와 같은 여러 Label을 다룬다.
```

## Unsupervised learning
* unlabelled data
* 모델로 하여금 이전에 발견되지 않은 스스로 패턴과 정보를 발견하도록 한다. 
