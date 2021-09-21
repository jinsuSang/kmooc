# Brief Introduction to Internet Functions

## Performance Metrics 성능 지표

- 지연 시간
- 패킷 손실률 
- 전송률

 ### 지연 시간

지연 시간 = 처리 지연 + 큐 대기 지연 + 전송 지연 + 전파 지연

1. Queue-ing delay
   - 버퍼 대기 시간
   - La/R (a - average packet arrival rate)

2. Transmission delay
   - L/R (L - 패킷 길이, R - 링크 bandwidth)

3. Propagation 
   - d/s (d - 물리적 링크 길이, s - 시그널 속도)

### 패킷 손실

- 가득찬 큐에 도착한 패킷은 버려진다
- 손실된 패킷은 이전 노드로부터 재전송된다

---

## 프로토콜 스택

| 프로토콜 스택     | 종류                                                         |
| ----------------- | ------------------------------------------------------------ |
| 애플리케이션 계층 | FTP, SMTP, HTTP                                              |
| 표현 계층         | encryption, data compression, machine-specific, encoding     |
| 세션 계층         | synchronization, connection management, recovery of data exchange |
| 전송 계층         | TCP, UDP                                                     |
| 네트워크 계층     | IP, routing protocols                                        |
| 데이터 계층       | 이더넷, 와이파이, PPP                                        |
| 물리 계층         | 유선 링크, 무선링크 (비트 정보)                              |

- 레이어를 사용하는 이유는 시스템 개발, 유지, 업데이트를 위해서이다.
- 그런데 레이어를 정확하게 나누어서 정해진 정보만을 주도록 설계가 되어 있기 때문에 효율성을 떨어뜨리는 단점도 있습니다.

---

## 네트워크 보안

- 인터넷은 보안을 고려하지 않고 설계되었다

	### Malware

- virus: 개체(이메일 등) 을 받거나 실행시킴으로써 감염된다
- worm: 스스로 실행되는 개체를 받음으로써 감염된다

- malware 는 키보드 입력을 가로채거나 어떤 곳에 접속하는지, 방문 사이트 정보, 패스워드 등을 탈취한다

### Packet Sniffing

- 지나가는 패킷을 읽어들인다

### Distributed Denizal of Service (DDoS)

- 분산 서비스 거부 공격
- 서버에 많은 트래픽을 보내 정상적인 서비스가 못하도록 한다

### Fake Addresses

- 패킷을 가짜 주소로 보내도록 한다 
- Sybil attack

### Fake WiFi Access Point

- 가짜 AP 를 사용하여 사용자 비밀정보를 훔친다

---

## 인터넷 역사

-- 생략

---

## Keyword

\- ISO/OSI 7 계층 : ISO에서 7개의 계층으로 정의한 개방형 시스템 통신 구조

\- 물리 계층(physical layer): 전파 또는 전기 신호를 전달하기 위한 모듈레이션(modulation)과 디모듈레이션(demodulation) 기술을 정의한 계층

\- 데이터 링크 계층(data link layer): 직접 연결된 이웃 노드와의 원활한 통신을 위한 규칙을 정의한 계층

\- 네트워크 계층(network layer): 패킷이 출발지에서 목적지까지 도달하기 위해 필요한 규칙을 정의한 계층

\- 전송 계층(transport layer): 종단 프로세스 통신에 필요한 전송 규약

\- 전파 지연(propagation delay): 송신기에서 한 프레임의 첫 번째 비트가 출발하여 수신기까지 도달하는 시간

\- 전송 지연(transmission delay): 한 프레임의 첫 번째 비트부터 마지막 비트를 전송 매체에 싣는 데 걸리는 시간

\- 처리량(throughput): 단위 시간당 데이터 처리의 총량 

