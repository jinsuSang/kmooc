# Transport Layer Services

## Transport-layer Services

### Program

- an executable file containing the set of instructions written to perform a specific job
- stored on a disk

### Process

- an executing instance of a program
- resides on the primary memory
- several processes related to same program at the same time

### Thread

- the smallest executable unit of a process 

### Transport Layer Function

- Transport Layer
  - logical communication between processes

- Network layer
  - logical communication between hosts

Internet => IP, Transport => TCP, UDP

컴퓨터에게 IP를 사용해 전송하고 프로그램으로 TCP 로 전달 \

- send side
  - application message fragmentation into segments
  - segments passing to network layer

- recv side
  - segments reassembly into messages

### TCP vs UDP

#### TCP

- Transmission Control Protocol
- Reliable, in-order delivery
- Connection -oriented service
- error control
- flow control
- congestion control

#### UDP

- User Datagram Protocol
- Unreliable, unordered delivery
- Connectionless service 
  - faster then TCP

## Multiplexing Socket

### Multiplexing and Demultiplexing

#### Multiplexing at sender

- sending data from its own multiple applications through network

#### Demultiplexing at receiver

- delivering data packets to their appropriate receivers among its own multiple applications

### How Demultiplexing Works

- Port number
  - different applications are assigned different port numbers
  - transport layer segments have fields for src/dst port numbers in common
  - used for differentiating segments

- However, the transport layer must be instructed by the application which process on which host should be the destination

### Socket

- Process sends/receives messages to/from its socket

  

## User Datagram Protocol

- Connectionless service
  - each UDP segment handled independently of others
  - Unrelialbe: UDP segments may be lost or delivered out-of-order to app

- use
  - streaming multimedia apps
  - DNS
  - SNMP

- Reliable transfer over UDP

  - add reliablity at application layer

  - application-specific error recovery

#### Advantages of UDP

- no connection establishment
- simple: no connection state at sender, receiver
- small header size
- no congestion control: UDP can blast away as fast as desired

### checksum

- sender
  - 16 bit integer checksum code of segment contents including header

- receiver
  - compute checksum of received segment
  - check if the computed checksum equals all 1's or not

## TCP

### Principles of Reliable Data Transfer

- Services abstraction (provided to the upper-layer) through a reliable channel
  - no corruption and no lost of data
  - delivered in the order in which they were sent

### Error Type and Solution

#### bit error

- checksum
- ack 

#### Packet loss

- Timeout of sender's timer
- Packet retransmission
- Packet sequence number for 
  - ordered delivery
  - data duplication prevention 

### Communication Error Recovery

- Packet retransmission method
- ARQ automatic repeat request
  1. Stop and wait
     - sender send one packet then waits for receiver response
     - after receiving ACK, sender resumes transmission
     - if timer expires without receiving ACK, sender retransmits the previous packet 

### Pipelined Protocols

#### Go-back-N

- sender can have up to N unacked packets in pipeline
- receiver only sends cumulative ack
- sender has timer for oldest unacked packet
  - when timer expires, retransmit all unacked packets
- Window of up to N, consecutive unacked packets allowed
- Cumulative ACK: acknowledges all packets up to 
- Timer for oldest in-flight packet, send_base

#### Selective repeat

- Sender can have up to N unacked packets in pipeline
- receiver sends individual ack for each packet

- Sender has timer for each unacked packet 

- Sender only resends packets for which ACK not received
- Receiver individually acknowledges all correctly received packets

