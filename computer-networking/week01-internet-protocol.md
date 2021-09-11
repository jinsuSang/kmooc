# The Internet and Protocol

## What is the Internet?

- Internet = Inter + network, network of networks

### 인터넷 구성요소

- 하드웨어

  end hosts, links, interconnection devices

- 소프트웨어

  운영체제, 애플리케이션, 프로토콜 

## Communication Protocol

### 프로토콜

- 컴퓨터 네트워크에서 데이터 전송 방식을 결정하는 규칙 집합 

- 정의 내용
  - 메시지 형식
  - 메시지 전송 및 수신 순서
  - 메시지 교환에 따른 동작 방식

##  Network Edge

### Network Structure

- Network edge
  - hosts: clients and servers
  - 데이터 센터 서버

- Network core
  - 상호연결된 라우터나 스위치

### Access Networks

- end system 에서 edge router 로 네트워크가 연결되는 방법
- residential access net
- institutional access nets
- wireless access nets

### Residential Access net

- DSL - Digital subscriber line
- Cable
- FTTH - Fiber to the home, 광케이블 

 ### Institutional Access net

- Ethernet 

### Wireless Access Networks

- Wireless LAN
- Cellular network

## End Host

- 애플리케이션 메시지 수신
- 패킷 단위로 데이터 나누기
- access network 로 패킷 전송 

## Communication Link

### Wired

- twisted pair 쌍꼬임선 - 100Mbps ~ 10Gbps
- coaxial cable 동축 케이블 - broadband, multiple channels on cable
- optical fiber 광케이블 - high speed, low error, 전자기적 잡음에 영향을 받지 않음

### Wireless

- WiFi - 2.4 GHz, 5 GHz
- IMT-Advanced (4G LTE) - about 2 GHz
- IMT-2020 (5G) - 30 GHz~300 GHz
- Satellite communication - 1~40 GHz

## Network Core

- Circuit Switching - 회선 교환
  - 출발지와 도착지 사이의 경로를 설정한다
  - 데이터 흐름은 물과 같이 이어진다 
- Packet Switching - 패킷 교환
  - 전체 데이터가 작은 패킷으로 나누어진다
  - 각 패킷은 도착지 주소가 있다
  - 각 패킷은 독립적으로 취급된다

### 회선 교환

- 자원들이 각 요청마다 할당된다
- 전화 네트워크에 사용되었다
- 채널 할당 방법 - FDM(주파수), TDM(시간)

### 패킷 교환

- 패킷은 모든 링크 capacity 에서 전송한다

- L/R 초로 L 비트 패킷을 R bps 로 전송한다 

- store-and-forward 저장 및 전달

  정보가 중간 스테이션으로 전송되어 나중에 최종 목적지 또는 다른 중간 스테이션으로 정보가 전송되는 통신 기술입니다.  네트워킹 컨텍스트의 중간 스테이션 또는 노드는 메시지를 전달하기 전에 메시지의 무결성을 확인합니다.

- End-end delay - 2L/R

### 교환 방식 비교

- 패킷 교환 방식은 더 많은 사용자를 수용한다
- 회선 교환 방식은 각 요청마다 동일한 서비스 질을 보장한다 
- 패킷 교환 방식은 데이터 손실과 큐 대기가 발생한다

## Internet Structure

- End system 은 acccess ISP (Internet Service Providers) 로 인터넷에 접근한다
- Access ISPs in turn must be interconnected 
- Resulting network of networks is very complex

### Traceroute

- sends three packets that will reach router i on path towards destination
- router i will return packets to sender
- shows interval between transmission and reply

```bash
$ tarcert google.com
```



