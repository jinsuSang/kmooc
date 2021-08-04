# 지도 학습과 Decision Tree

## supervised learning 이란?

- 기본적으로 데이터와 라벨을 모두 활용하는 머신러닝 기법

- feater와 label로 구성된 모든 데이터는 지도학습 데이터로 활용

### 지도학습 목표

- 어떤 feature가 주어졌을 때 그에 대응하는  label을 결정하는 것
- 라벨을 학습 데이터에 제공하고 유사 라벨을 최종적으로 얻는 것

### Decison Tree란?

- 종류가 매우 다양함
- 응용 분야와 사용자 요구에 따라 변환해 사용하는 알고리즘
- 조건을 만족하느냐, 만족하지 않느냐에 따라 두 개로 분류하는 과정을 계속 거치면서 나누는 알고리즘
- feature  타입, 임계치(threshold) 값 결정, 학습 중단조건(stop criterion)에 따라 종류가 다양해짐

### 최적 방법

- 주어진 데이터를 두 개의 나뉜 데이터가 서로 개수가 비슷하도록 나눔
- 나눴을 때 정확도가 높은 방향으로 나누는 방법
- 나눴을 때 단 한 개의 샘플만 한쪽으로 가고 나머지는 반대록 가게 하는 방법
  - 트리 높이가 너무 길어짐
  - 트리가 한 쪽으로 쏠림
  - 스플릿이 많이 필요함

### split 계산

- 샘플 n 개, feature d개, thresholds k개
- n * d * k

### Decision Tree를 학습하는 방법은 무엇인가?

- 샘플이 많은 경우 - 학습 시간이 매우 길어지게 될 것임
- feature 타입이 많거나 임계값을 세세하게 나눌 경우 - 계산량이 점점 늘어나게 될 것임

#### 방법

- 모든 계산을 동시에 진행하지 않음
- 각 노드 계산시 피쳐 타입의 경우 랜덤하게 결정하는 방안을 많이 사용
- 임계값 나누는 기준을 2 ~ 3 개 정도로 적게 해서 계산량을 줄이는 방법 사용

####  Split Node 1개당 계산량

- Split Node는 많은 조합의 Split Node이 다시 섞임
- 모든 Split Node 조합까지 고려하면 의사결정 나무 학습 불가능
- 일반적으로  greedy recursive splitting 전략 사용

#### greedy recursive splitting

------

## 지도학습의 일반화 성능

### 지도 학습의 일반화 성능이란?

#### split Node를 언제까지 나눌 것인가?

- 일반화 성능을 결정하는 부분
- Split Node를 현재 주어진 데이터를 최대한 나눌 때까지 학습하는 방법
  - 학습 성능 100%
  - 학습 데이터에 대한 성능 하락 -> 계산량이 점점 증가함
- 최대한의 Split Node 개수에 제한을 거는 방법

#### Overfitting 과적합

- 최대한 Decision Tree를 나누면 테스트 정확도가 떨어짐
- 과적합이란 학습 정확도는 매우 높은 반면 테스트 정확도가 상당히 떨어지는 상태
- 새로운 데이터가 들어왔을 때 정확한 라베을 예측하는 것이 어려움
- 특징을 배우는 게 아니라 다양한 상황을 일반화시키는 학습 방법이 필요함
- 테스트 데이터는 학습 과정에서 고려되어서는 안되는 데이터임

### 지도 학습의 일반화 성능은 어떻게 향상시킬까?

- 학습 데이터와 테스트 데이터는 서로 비슷하다고 가정 

- IID (Independent and Identically Distributed) - 학습과 테스트 데이터가 같은 샘플 분포에서 나옴

  ### 과적합 overfitting

  - Approximation 오류가 클수록 과적합 정도가 심하다고 봄 - 테스트 오류와 학습 오류의 차로 계산함

   -  오류가 크면 정확도가 떨어지고 과적합이 발생했다는 것을 의미함
   -  테스트 정확도와 학습 정확도 차이를 활용해 과적합 정도를 계산함
   -  데이터가 적은 경우 과적합이 쉽게 발생함
   -  decision tree depth 가 큰 경우 오버피팅이 크게 발생함

  ### 테스트 데이터에서의 높은 성능 예측하기

  - Validation Error 
    - 모든 데이터를 학습에 활용할 수 있음
    - 학습데이터를 나누어 validation 데이터를 추가로 구성함
    - 학습데이터에서 일부분 추출

  - [K-fold Cross Validation 교차 검증](http://mlwiki.org/index.php/Cross-Validation)
    - K가 3인 경우 세 번의 머신러닝 모델 학습
    - 한 개만 검증 셋으로 활용하면 3가지 종류의 학습 데이터와 검증 셋 모임으로 나뉘게 됨
    - 서로 다른 검증 오류 값들의 평군이 가장 작게 하는 모델을 찾는 방법

### Parameter와 Hyper-parameter는 무엇인가?

- Parameter - 머신러닝 알고리즘을 통해서 얻어진 값

-  Hyper-parameter - 사용자가 정해줄 수 있는 값, 사용자가 다루는 유일한 값

- Cross Validation Error 가 가장 작아지는 Hyper-parameter를 찾아야함

- Cross Validation Error 가 작을수록 일반화 성능이 높아짐

  #### Decison Tree 예시

  - Parameter - Feature 타입, Threshold

  - Hyper-parameter - Split Node 개수

    

