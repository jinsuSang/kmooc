# Network Layer Services

## Overview of Network Layer

### Network Layer

- Transport segment from sending to receiving host
- Sending side encapsulates segments into datagrams and sends them
- Network layer protocols in every host and router

#### Routing

- 출발지부터 목적지까지 경로 설정

#### Forwarding

- 패킷을 라우터에서 적당한 라우터로 옮기는 과정 

### Traditional IP network VS Software-defined network SDN

- Traditional IP network

  routing and forwarding at the same system

- SDN

  routing and forwarding separated at different systems

## Inside of Router

### Input Port Functions

- Physical layer: bit-level reception
- data link layer: Ethernet 
- Decentralized switching
  - using header field values, lookup output port using forwarding table in input port memory 
  - goal: complete input port processing at line speed
  - queuing: if datagrams arrive faster than forwarding rate into switch fabric

### Queuing

- Head-of-the-Line HOL blocking: queued datagram at front of queue prevents others in queue from moving forward

### Switching Fabrics

Switching Rate : rate at which packets can be transfer from inputs to outputs

 1. Switching via Memory

    speed limited by memory bandwidth, 2 bus crossings per datagram

2. Switching via Bus

   Bus contention: switching speed limited by bus bandwidth

3. Switching via Interconnection Network

   fragmenting datagram into fixed length cells, switch cells through the fabric

### Output Port Functions

- Buffering required when datagrams arrive from fabric faster than the transmission rate
- Scheduling discipline choose among queued datagrams for transmission

#### Scheduling Mechanisms

- Scheduling : choose next packet to send on link
- FIFO : send order of arrival to queue
- Discard Policy
  1. tail drop : drop arriving packet
  2. priority : drop/remove on priority basis
     - sending highest priority queued packet
     - Multiple classes with different priorities
     - class may depend on marking or other header info
  3. random : drop/remove randomly

- Round Robin 
  - Multiple Classes
  - Cyclically scan class queues, sending one complete packet from each class 

- Weighted Fair Queuing WFQ Scheduling
  - Generalized Round Robin
  - Each class gets weighted amount of service in each cycle 
