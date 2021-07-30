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