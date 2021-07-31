# 머신러닝을 위한 표현법

## 머신러닝이란 ?

- 패턴 인식 Pattern Recognition
  - 데이터에서 어떤 특징을 추출하는 알고리즘
  - 데이터 분류 방법에 따라 특징이 달라짐
  - 데이터 마이닝과 머신러닝으로 나뉘어짐
    - 데이터 마이닝 - 특징 자체에 관심을 가짐, 분류할 수 있는 최적의 방법을 찾아볼 수 있음, 사람의 결정을 도움
    - 머신러닝 - 사람이 하고 있거나 데이터에 주어진 것을 그대로 수행함, 사람의 결정을 모방함
      - 특정 상황에 맞는 행위 수행
      - 사람이 일하기 위험한 환경에서 수행하는 경우
      - 인텔리전트 서베일런스 시스템 - 인공지능이 탑재된 CCTV
      - 키워드 기반 영상 추천 시스템
      - <u>**수많은 데이터에서 자동으로 적절한 특징을 선택**</u>

## 데이터와 그 표현법

- 데이터 안에 다양한 feature가 구성됨

###  feature 구분

- categorical features
  - binary feature - 0 or 1
  - nominal feature - 범주형 자료 ex) M, F
- numerical features
  - discrete counts - 고정된 값을 가지는 내용 ex) 연도
  - ordinal featuers -순서가 정해져 있음 ex) 랭킹
  - continuous / real-valued features - 연속형 / 현실 세계 값

-  특징들의 분류가 명확하게 나뉘어지지 않지만 머신러닝 적용을 위해 데이터 종류와 상황에 따라 활용방법 변형

### [Bag of words](https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%96%B4_%EA%B0%80%EB%B0%A9_%EB%AA%A8%EB%8D%B8)

- 샘플을 표현하는 특징이 바로 단어에 해당하는 카운트 값
- 입력 데이터는 머신러닝에 적합한 형태로의 변환 과정이 필요

### Adjacency matrix

- 그래프의 관계를 테이블 형식으로 바꾸어 feature로 사용함

## 데이터를 바꾸는 법

- 데이터 활용 방법에 따라 특징을 변환하는 방식이 다양함
  1. 특징 통합 feature aggregation
  2. 특징 선택 feature selection
  3. numerical data -> categorical 형식으로 변환
  4. 특징 크기 조절 feature Scaling - 작은 값들도 상대적으로 분류성이 커져서 효율성을 높임
  5. 여러 특징의 평균 값을 활용하는 경우 데이터가 많이 줄어들고 이미지에 해당하는 대표값을 가져 효율성을 높임 ex) 전체 feature 평균, 전체 features의 분산값
- 머신러닝 기법에 적용하기 위해 데이터를 변경시 주의해야함

## 머신러닝의 수학적 기초

### 머신러닝의 기본 표현법

- 특징과 라벨 feature and label prediction - 데이터에 해당하는 feature를 n*d 매트릭스 형태로 표현 (n: 라벨, 행 d: feature 개수, 열)
- 라벨 - 머신러닝을 통해 얻고자 하는 결과값, 사용 방향이나 목적에 따라 다양해짐

### 머신러닝 기본 분류

- Generative Model 
  - 샘플을 확률적으로 표현, 일반화
  - 문제점 - 기존에 사용된 샘플들과의 거리 값을 기준으로 분류하기 때문에 새로운 feature 혹인 예외값이 입력되면 결과값이 제대로 나오지 않음, 명확한 결론을 도출하기에는 적합하지 않음
  - 분류
    - Parametric Model - 어떤 거리 값을 기반으로 값을 도출(제한된 개수의 값을 활용)
    - Non Parametric Model - 거의 모든 샘플들을 활용하는 모델 (데이터 개수에 비례한 개수의 값을 활용)

- Discriminative Model

  - 일반적, 직관적
  - decision boundary 
    - 두 가지 종류의 샘플이 존재할 때 두 가지 샘플을 분류할 수 있는 선을 찾는 것 
    - 두 개를 구분 할 수 있는 정확한 분류 방식을 찾는 과정

  * 장점 - 완전히 다른 샘플이 입력되더라도 0과 1 형태로 출력
  * 선 하나 긋는 모델
    - Least Square
      - 모든 샘플들 간의 거리를 기반으로 가운데 선을 찾는 과정
      - 샘플들 간의 거리를 최소화하는 선을 찾음
      - 잘못된 샘플이 존재한는 경우 결과가 틀릴 수 있음
      - 잘못되거나 특이한 샘플을 제거하는 방식을 사용하여 해결
    - Support Vector Machine
      - 가장 가까이 있는 샘플 두개를 집어서 그 가운데를 가로지르는 선을 도출
      - 맥시멈 마진이라고 함
      - 상대적으로 정확한 결과 값을 얻을 수 있음

  - linear  모델

    곡선을 배제하고 선을 사용해 분류함

    - [선형 분류기 linear classifier](https://ko.wikipedia.org/wiki/%EC%84%A0%ED%98%95_%EB%B6%84%EB%A5%98) - 선형 회귀자 같이 계산된 값을 0 혹은 1로 변경하여 카테고리 라벨을 생성

      - ![y=f({\vec {w}}\cdot {\vec {x}})=f\left(\sum _{j}w_{j}x_{j}\right),](https://wikimedia.org/api/rest_v1/media/math/render/svg/4b3c233b748fa77e9132685b0574a69e92aa1899)

        y: 라벨값(결과값), w: 선형 모델, x: 특징 값

        x와 y는 정해진 값이지만 w는 머신러닝 목표값인 선형모델이다 

    - [선형 회귀자 linear regressor](https://ko.wikipedia.org/wiki/%EC%84%A0%ED%98%95_%ED%9A%8C%EA%B7%80) - 점수 추정할 때 사용, 0 이나 1로 결과 얻기 힘듬

      - y = w * x 

  - 정칙화 Regularization 와 비선형성 Nonelinearity

    - [Regularization](https://junklee.tistory.com/29) - w 값 자체에 적용되는 값

      - 데이터에는 영향을 주지 않음
      - w 값에 대한 제한을 거는 존재가 Regularization
      - 데이터에 어느 정도 노이즈가 존재하느냐의 문제에 초점
      - 데이터에 노이즈가 있더라도 학습된  w 가 노이즈의 효과를 감소시킴
      - 선형 모델 자체가 노이즈에 대한 강인함을 갖도록 생성
      - 방법
        - L1-norm regularization
        - L2-norm reguarization

      - 새로운 샘플이 들어왔을 때 샘플에 대한 정확도가 떨어질 가능성 증가
      - 특정 feature 크기가 너무 크지 않도록  norm 값을 적용하여 크기 값이 전반적으로 고르도록 유도함

    - Nonelinearity - 선 하나로 분류할 수 없는 상황

      - 특정 점을 기준으로 거리 값을 feature로 사용

      - 머신러닝 효율성을 위해 feature를 특정점 기준 거리로 변경함

        

    

    

    

