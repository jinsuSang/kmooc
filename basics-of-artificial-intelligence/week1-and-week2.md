# 인공지능 기초 1주차, 2주차

## 인공지능 소개

#### 지능이란?

- 관점에 따라 지능을 쉽게 정의하기 힘들기 때문에 인공지능을 정의하기 힘들다
- 지능이라고 불리기 위해 갖추어야하는 요건을 정하기도 하지만 이도 관점에 따라 어렵다 

#### 인공지능을 바라보는 관점

- 사람처럼 구현
- 이성적으로 구현  

#### 사람 처럼은 이성적으로 구현하는 것과 무엇이 다른가?

- 상식을 가지고 있다
- 사회적 행동을 보인다
- 전문 지식이 있다
- 문제 해결 능력이 있다

#### 지능적 생각은 지능적 행동과 무엇이 다른가?

- 지능은 정의하기 쉽지 않지만 지능적 행동은 정의하기 쉽다
- Turning test
  - [튜링 테스트](https://ko.wikipedia.org/wiki/%ED%8A%9C%EB%A7%81_%ED%85%8C%EC%8A%A4%ED%8A%B8)
  - Acting humanly
  - 여러 지식을 컴퓨터가 내부적으로 표현할 수 있어야 된다
  - 내가 가지고 있는 지식들을 바탕으로 가지고 있지 않은 지식에 대한 질문이 있을 때 추론해서 대답해야 한다
  - 학습을 통해 새로운 지식을 계속 습득해야 한다 
  - 조사관의 질문을 이해하고 말로 표현해야 한다  

#### 인공지능 주요 주제

![image-20210919101030659](C:/Users/sangjs/AppData/Roaming/Typora/typora-user-images/image-20210919101030659.png)

#### 강 인공지능과 약 인공지능

- 약 인공지능은 사람이 프로그래밍을 하고 특정 상황을 판단한다 
- 강 인공지능은 사람을 모방하지 않고 자유의지와 자각을 갖춰야 한다

#### Technological Sigularity 특이점

- 약 인공지능 관점에서 특이점은 빠르게 오고 있으나 강 인공지능에서는 아직 멀었다

---

## 문제 해결 및 탐색 전략

## Uninformed Search

1. BFS
2. Uniform-cost search
3. DFS
4. Depth-limited search
5. Iterative deepening search

### Breadth First Search

- FiIFO Queue
- complete but expensive

### Depth First Search

- LIFO Stack
- cheap but incomplete

|           | BFS      | DFS    |
| --------- | -------- | ------ |
| Complete? | Y        | N      |
| Time      | O(b^d+1) | O(b^m) |
| Space     | O(b^d+1) | O(b^m) |
| Optimal?  | Y        | N      |

 
