# Transmission Control Protocol

## TCP

- Point - to Point
- Connection - oriented service
  - reliable transfer, in-order delivery
  - handshaking initializes sender and receiver state before data exchange

- Pipelined transmission
  - window size is set by TCP congestion and flow control
  - congestion control: transmission rate controlled not to make congestion in network
  - flow control: sender will not overwhelm receiver
  - MSS : maximum segment size

- full-duplex connection
  - bi-directional data flow in same connection

## Sequence and Acknowledgement Number

- Sequence number
  - byte stream "number" of first byte in segment's data

- Acknowledgement number
  - sequence number of the next segment expected by receiver
  - cumulative ACK

### TCP Reliable Data Transfer

- TCP creates reliable data transfer service on top of IP's unreliable service
  - pipelined segments
  - cumulative acks
  - single retransmission timer

#### TimeoutInterval = EstimatedRTT + "safety margin"

## Fast Retransmit

- Timeout period often relatively long
  - long delay before resending local packet

- Another way to detect segment lost
- sender receives 3 duplicate ACKs (except first normal ACK) for same data, resend unacked segment with smallest sequence
- TCP retransmissions triggered by
  - timeout events
  - duplicate acks

## TCP Flow Control

Receiver controls sender, so sender won't overflow receiver's buffer by transmitting too much, too fast

## Congestion Control

### Network Congestion

Too many sources sending too much data too fast for network to handle

congestion control is global issue

flow control is point-to-point issue

- Manifestations:
  - lost packets buffer overflow at routers
  - long delays queueing in router buffers 

### overview

- AIMD approach: sender increases transmission rate (window size), proving for usable bandwidth until loss occurs
  - additive increase: increase cwnd by 1 MSS every RTT until loss detected
  - multiplicative decrease: cut cwnd in half after loss 

- congestion window (cwnd)

  - the rate a TCP sender can send traffic (the amount of packets in transit)

    LastByteSent - LastByteAcked <= min(cwnd, rwnd)

- cwnd is dynamic

### slow start

- when connection begins, increase rate exponentially until first loss event
- initially cwnd = 1 MSS
- double cwnd every RTT
- done by incrementing cwnd for every ACK received

- Summary: initial rate is slow but ramps up exponentially fast

### Congestion Avoidance

on loss event, ssthresh is set to 1/2 of cwnd just before loss event

surpassing ssthresh, cwnd increases by just a single MSS every RTT

ssthress 이후 1 MSS 씩 증가한다



## TCP Congestion Control Algorithm

### Tahoe

- slow start
- congestion avoidance
- fast retrasmit
- slow start begins 1 on timeout and fast retransmits

#### limitation of tahoe

- no differentiates losses indicated by timeout and duplicate ACKs
- always sets cwnd to 1 MSS

#### Two responses to packet losses by Reno

- loss indicated by timeout
  - cwnd set to 1 MSS
  - slow start to ssthresh then congestion avoidance begins

- loss indicated by fast retransmit
  - cwnd cut in half
  - fast recovery, then congestion avoidance

### Fast Recovery

Half cwnd maintained until a non-duplicate ACK is received

- amount of packets in transit kept from decreasing more than expected

  

## TCP vs UDP

TCP fairness through AIMD (additive increase and multiplicative decrease)

- two competing sessions

- multimedia apps often do not use TCP
- do not want rate throttled by congestion control
- Instead use UDP
  - send audio/video at constant rate, tolerate packet loss 

## Summary

-  연결지향(connection-oriented): 송/수신기 사이의 물리적인 연결이 아닌 논리적인 연결을 의미하는 개념

- 핸드셰이크(handshake): 통신 관련 분야에서 둘 이상의 장치가 연결/단절을 위해 선행하는 약속된 협상 과정

- 최대 세그먼트 크기(Maximum Segment Size, MSS): TCP가 세그먼트 한 개로 보낼 수 있는 최대 데이터 크기

- 전이중 통신(full-duplex): 송신과 수신이 동시에 가능한 통신 방식(참조: https://ko.wikipedia.org/wiki/이중통신)

- 혼잡 윈도우(congestion window): 송신측에서 ACK 수신 없이 연속적으로 전송할 수 있는 최대 데이터 양

- AIMD (Additive Increase and Multiplicative Decrease): 혼잡 윈도우(congestion window)를 증가시킬 때는 선형적으로, 감소시킬 때는 지수적으로 감소시키는 TCP 혼잡제어의 기본 원칙 (https://en.wikipedia.org/wiki/Additive_increase/multiplicative_decrease)

