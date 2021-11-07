# Infra-/Inter-AS Routing and SDN

## Intra AS Routing OSPF

### Scalability of Routing

![image-20211107160646587](week08-infra-inter-as-routing-and-sdn.assets/image-20211107160646587.png)

### Autonomous System

![image-20211107160921641](week08-infra-inter-as-routing-and-sdn.assets/image-20211107160921641.png)

![image-20211107160935152](week08-infra-inter-as-routing-and-sdn.assets/image-20211107160935152.png)

### Internet Approach to Scalable Routing

![image-20211107161418251](week08-infra-inter-as-routing-and-sdn.assets/image-20211107161418251.png)

### Interconnected Ases

![image-20211107161522791](week08-infra-inter-as-routing-and-sdn.assets/image-20211107161522791.png)



### Routing Protocols

![image-20211107161636431](week08-infra-inter-as-routing-and-sdn.assets/image-20211107161636431.png)

### OSPF

- open shortest path first
- open => publicly available

![image-20211107161735616](week08-infra-inter-as-routing-and-sdn.assets/image-20211107161735616.png)

![image-20211107161912192](week08-infra-inter-as-routing-and-sdn.assets/image-20211107161912192.png)

![image-20211107162117841](week08-infra-inter-as-routing-and-sdn.assets/image-20211107162117841.png)

![image-20211107162227658](week08-infra-inter-as-routing-and-sdn.assets/image-20211107162227658.png)



## Inter AS Routing BGP

### Inter-AS Tasks

![image-20211107162946775](week08-infra-inter-as-routing-and-sdn.assets/image-20211107162946775.png)

![image-20211107163133704](week08-infra-inter-as-routing-and-sdn.assets/image-20211107163133704.png)

![image-20211107163204807](week08-infra-inter-as-routing-and-sdn.assets/image-20211107163204807.png)

![image-20211107163411105](week08-infra-inter-as-routing-and-sdn.assets/image-20211107163411105.png)

![image-20211107163914180](week08-infra-inter-as-routing-and-sdn.assets/image-20211107163914180.png)

![image-20211107164041960](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164041960.png)

![image-20211107164110403](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164110403.png)

![image-20211107164142719](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164142719.png)

![image-20211107164255491](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164255491.png)

![image-20211107164317821](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164317821.png)



## Software Defined Networking

![image-20211107164657371](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164657371.png)

![image-20211107164835172](week08-infra-inter-as-routing-and-sdn.assets/image-20211107164835172.png)

![image-20211107165104166](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165104166.png)

![image-20211107165209954](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165209954.png)

![image-20211107165234138](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165234138.png)

## OpenFlow

![image-20211107165410612](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165410612.png)

![image-20211107165504616](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165504616.png)

![image-20211107165607847](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165607847.png)

![image-20211107165641670](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165641670.png)

![image-20211107165726244](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165726244.png)

![image-20211107165739741](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165739741.png)

![image-20211107165754307](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165754307.png)

![image-20211107165822206](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165822206.png)

## Internet Control Message Port

![image-20211107165859835](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165859835.png)

![image-20211107165917089](week08-infra-inter-as-routing-and-sdn.assets/image-20211107165917089.png)



## Keyword

\- Autonomous System (AS): 명확한 라우팅 정책을 가지고 동일한 네트워크 관리 주체에 의해 관리되는 네트워크, 네트워크의 집합 또는 도메인(domain)

\- AS 내부(Intra-AS) 라우팅: 같은 AS 내에 있는 라우터 간의 라우팅

\- AS 간(Inter-AS) 라우팅: 서로 다른 AS에 속한 라우터 간의 라우팅으로 사실상 표준인 Border Gateway Protocol (BGP)가 대표적임. 다른 도메인 간에 라우팅이 이루어지므로 성능보다 라우팅 정책이 중요함.

\- 소프트웨어 정의 네트워크(Software-Defined Network, SDN): 소프트웨어 기반의 중앙집중형 컨트롤러에 의해 유동적인 라우팅, 부하 균형(load balancing) 및 접근 제어가 가능한 새로운 네트워크 구조

\- 오픈플로우(OpenFlow): SDN 컨트롤러와 스위치 간의 통신 규약을 정의하는 대표적 Application Programming Interface (API)

\- 인터넷 제어 메시지 프로토콜(Internet Control Message Protocol, ICMP): 라우터를 포함한 네트워크 장비가 제어 정보를 보낼 때 사용하는 프로토콜로서 주로 오류 보고(error reporting) 메시지를 보냄

