# 인공지능 기초 3주차

## 휴리스틱 탐색 및 지역 탐색

### Best-First Search

- 각 노드를 평가하는 함수를 사용하자

- 가장 적당한 노드를 먼저 접근한다

- Greedy best-first search

  - Evaluation Function `f(n) = h(n) 휴리스틱`

    node n 부터 목표 지점까지 가장 낮은 비용을 측정한다 ]

- A* Search (A-start)

  - Evaluation Function `f(n) = g(n) + h(n)`

    g(n) - n까지의 비용

    h(n) - n에서 목적지까지의 예상 비용

    f(n) - n 을 통한 목적지까지의 예상 비용

  - 이미 비용이 높은 경로를 확장하는 것을 피한다
  - optimal solution
    - Admissible Heuristics (인정되는 휴리스틱)
      - A heuristics h(n) is admissible if for every node n, `h(n) <= h*(n)` where h*(n) is the true cost to reach the goal state form n

### 지역 탐색 알고리즘

[안경잡이 개발자 블로그](https://blog.naver.com/ndb796/220578912459)

- local search algorithms
- 해결이 목적인 경우에 사용된다
- 메모리가 적게 사용된다 
- 무한 혹은 큰 공간 상태에서 최적해를 찾아낸다
- n-queens 문제 
- Hill-Climbing Search
  - <u>Steepest ascent</u> : at each step the current node is replaced by the best neighbor
  - <u>Greedy Local Search</u>: grabs a good neighbor state without thinking ahead about where to go next
  - 단점: 초기 상태에 의존적이며 local maximum 에 의해 global  maximum 을 찾지 못할 수도 있다

- 



