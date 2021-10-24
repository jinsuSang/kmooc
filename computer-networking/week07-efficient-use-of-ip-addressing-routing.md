# Efficient use of IP Address and Routing

## DHCP Dynamic Host Configuration Protocol

- Host dynamically obtains its IP address from network server when it joins network

#### Advantages of DHCP

- Efficient use of IP address
  - one solution to the IP address exhaustion problem

- Allow the plug and play of a computer system

## Network Address Translation

- NAT
- IP 패킷의 TCP/IP 포트 숫자와 소스 및 목적지의 IP 주소 등을 재기록하면서 라우터를 통해 네트워크 트래픽을 주고 받는 기술이다 
- 패킷에 변화가 생기기 때문에 IP 나 TCP/UDP 의 체크섬도 다시 계산되어 재기록해야 한다.

#### Port Forwarding

- statically configure NAT to forward incoming connection requests at giver port to server

## IPv6

#### IPv6 datagram format

- fixed-length  40 byte header
- no fragmentation allowed

#### IPv6 Datagram Format

- priority : identify priority among datagrams in flow

- flow label: identify datagrams in same flow

- checksum removed entirely to reduce processing time at each hop

#### Migration from IPv4 to IPv6

- Tunneling: IPv6 datagram carried as payload in IPv4 datagram among IPv4 routers

## Introduction to Routing

### Routing Protocols

- determine good paths from sending hosts to receiving host, through network of routers

#### Link State Routing

- Link-state advertisement message
  - neighbor node info
  - link info to neighbors

- Dijkstra's algorithm
  - Can happen when link cost equals the amount of carried traffic

#### Distance Vector Routing

- Bellman-Ford Equation

  

#### Distance Vector VS Link State

| Distance Vector                                      | Link State                                            |
| ---------------------------------------------------- | ----------------------------------------------------- |
| Entire routing table is sent as an update            | Incremental updates                                   |
| Slow convergence                                     | Fast convergence                                      |
| Updates are sent to directly connected neighbor only | Updates are broadcast to entire network               |
| Routers don't know the entire network topology       | Routers know the entire network topology of that area |
| Count-to-infinity problem                            | No routing loops                                      |
| Simple configuration                                 | Complex configuration                                 |
| RIP Routing Info Protocol                            | OSPF Open Shortest Path First                         |

