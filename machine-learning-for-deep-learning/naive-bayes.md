# 확률적 구분기와 Naive Bayes

## 확률적 구분기의 정의

- 확률적 구분기 - 확률값을 기반으로 두 물체를 구분하는 방법

  ### 지도 학습 테스트 성능은 어떻게 표현할까?

  | 예측값 / 실제 | spam            | not spam       |
  | ------------- | --------------- | -------------- |
  | spam          | True Positive   | False Positive |
  | not spam      | False  Negative | True Negative  |

  - `Precision` = TP / (TP + FP)
  - `Recall` = TP / (TP + FN)
  - Recall이 떨어지면 Precision 이 높아지고 Precision이 떨어지면 Recall이 상승한다
  - `Precision-Recall Curve` 를 이용한다. Precision, Recall 이 높을수록 좋은 머신러닝 모델이다.
  - `ROC curve` (Receiver operating characteristic curve, x축 False Positive Rate, y축 Recall) - Positive인 샘플들 중에서 False Positive라고 판별된 샘플들 비율, 적분값을 성능으로 판별하며 클수록 성능이 높다고 본다.
  - `F1 score` - Precision과 Recall의 조화평균값, 한 개 값으로 성능을 비교하고 싶을 때 사용한다
  - `Weighted F1 Score` - 멀티 클래스 문제를 해결하기 위해 사용된다. 각 클래스 별로 얻은 F1 score의 평균값이다.

  ### Random Variable

  - random variable- 확률에 의해 결정되는 변수

  ### 머신러닝을 위한 확률 계산 방법

  - [joint probability](https://goodtogreate.tistory.com/entry/%EC%A1%B0%EA%B1%B4%EB%B6%80-%ED%99%95%EB%A5%A0-Conditional-Probability) - 두 개의 사건, 두 개의 랜덤 변수가 동시에 발생하는 상황의 확률

  - [Marginalization Rule](http://ais.informatik.uni-freiburg.de/teaching/ss11/robotics/etc/probability-rules.pdf) - 어떤 A 라는 이벤트가 발생할 확률과 A와 X가 모두 동시에 발생하는 확률의 관계

  - conditional probability (조건부 확률) - A가 발생한 환경에서 B가 발생할 수 있는 확률

  - [Bayes Rule](https://ko.wikipedia.org/wiki/%EB%B2%A0%EC%9D%B4%EC%A6%88_%EC%A0%95%EB%A6%AC) - [참고](https://hyeongminlee.github.io/post/bnn001_bayes_rule/)

    ![](https://wikimedia.org/api/rest_v1/media/math/render/svg/87c061fe1c7430a5201eef3fa50f9d00eac78810)

  ### 확률적 구분기

  - feature가 주어졌을 때 확률이 0이나 1이될 확률을 구해 비교하는 방식이다.

## Naive Bayes

### Bayes Rule이란 무엇인가

​	![](https://wikimedia.org/api/rest_v1/media/math/render/svg/87c061fe1c7430a5201eef3fa50f9d00eac78810)

- likelihood - P(B|A)
- prior - P(A): 현재 목표로 하고 있는 이벤트가 발생할 확률
- marginalization - P(B): 현재 조건부인 이벤트가 발생할 확률
- Posterior - P(A|B)

- **posterior 와 likelihood의 컨디션과 목표로 하는 이벤트가 뒤바뀌었다는 점이 중요하다.**

### Naive Bayes

- 여전히 큰 피처 X의 다양성 문제를 해결하기 위한 것
- 각각의 서로 다른 피쳐들을 독립적이라는 가정 활용 