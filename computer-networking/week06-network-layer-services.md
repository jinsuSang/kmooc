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

## Internet Protocol Overview

### IP Fragmentation and Reassembly

- Network links have MTU (max, transfer size)
  - largest possible link - level frame

- Large IP datagram divided fragmented within network

  - one datagram becomes several datagrams

  - reassembled only at final destination

  - IP header bits used to identity, order related fragments

    

## *IP Addressing*

### Introduction to IP Address

- IP address: 32 bits identifier for host, router interface
- interface : connection between host/router and physical link

- IP address associated with each interface

### IP Address Class

- Class A : 0 ~ 127, host 24bits
- Class B : 128 ~ 191, host 16 bits
- Class C : 192 ~ 223, host 8bits

### subnets

- a logical subdivision of an IP network
- why?
  - Datagram forwarding performed by routers
  - Hosts in a same network can reach each other without intervening router
  - Too many hosts in a network increase maintenance overhead
  - Divide and Conquer

### subnet mask

- indicating the bits that will be used as the network number

### ***Classless inter-domain routing CIDR***

- supernetting

- Address format : a.b.c.d/x where x is # bits in network portion of address

  

## Datagram Forwarding

### IP Network = Datagram Network

- No call setup at network layer
- Routers: no state about end-to-end connections

#### Datagram forwarding

- destination-based forwarding
- generalized forwarding : forward based on any set of header field values SDN

### Longest Prefix Matching

- when looking for forwarding table entry for given destination address, use longest address prefix that matches destination address
