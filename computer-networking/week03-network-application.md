# Network Application

## Principles of Application

- Two kinds of application structures
  - Client-Server model
  - Peer to Peer P2P model 

### Client-Server model

- Server
  - always-on
  - permanent IP address
  - data centers for scaling

- Client
  - Communicate with Server
  - may be intermittently(간헐적으로) connected
  - may have dynamic IP address
  - do not communicate directly with each other 

### P2P

- no always-on server
- arbitrary end systems directly communicate
- self scalability - new peers bring new service capacity, as well as new service demands
- peers are intermittently connected and change IP address
- complex management

### Application Protocol

- Open Protocol
  - HTTP, SMTP

- Proprietary protocol
  - Skype

### TCP

- ***Error control*** : reliable transport between sending and receiving process
- ***Flow control***: sender won't overwhelm receiver
- ***Congestion control***: throttle sender when network overloaded
- Does not provide: timing, minimum, throughput guarantee, security
- Connection-oriented: setup required between client and server processes

 ### UDP

- Unreliable data transfer between sending and receiving process

---

## Web and HTTP

### HTTP

- HyperText Transfer Protocol
- Hyperlink: a reference to data the reader and directly follow by clicking

### RTT - Round-Trip-Time

### HTTP response time

- 2RTT + file transmission time 

### REST

- Representational State Transfer
  - HTTP should be stateless 
  - RESTful service: service that conforms to the REST architectural style

- Architectural constraints
  - client-server architecture: separation of the user interface concerns from the data storage concerns
  - statelessness
  - layered system
  - code on demand
  - uniform interface 

---

## Cookies and Web Caching

### Web Caching

- Browser set to access Web via cache
- All HTTP requests sent to cache
  - if the requested object in cache: cache returns the object to the client
  - cache requests the object from the origin server, then returns it to the client

- cache acts as both client and server

### Effect of Web caching

- for client, response time reduction
- for server (content provider), more user support
- for local ISP, efficient usage of access link bandwidth by reducing traffic to external server

---

## SSL TLS

- provides encrypted TCP connection at the application layer
- data integrity
- end-point authentication

### SSL

- Secured Socket Layer

### TLS Transport Layer Security

- the improved version of SSL 3.0
- more secure but little slower due to the two-step communication processes 
- server authentication and actual data transfer 

---

## Electronic Mail

-  components
  1. clients
  2. mail server
  3. protocols: SMTP, POP3, IMAP

### SMTP

- Uses TCP as the transport layer protocol for reliable email delivery from sending server to receiving server
- three phases of transfer
  - handshaking
  - transter of message
  - closure

- command/response interaction
  - commands: ASCII text
  - response: status code and phrase

### POP3

- Post Office Protocol 3
- deletes messages from the server after retrieving
- Disconnects from the server after download

### IMAP

- Internet Mail Access Protocol
- Keeps all messages at server and allows user to organize message folders
- synchronization across devices
- stays connected until the mail client app is closed and downloads messages on demand

---

## Domain Name System

### IP address

- 32 bit

###  Domain name system

- the most important part of the internet for internetworking
- DNS services
  - hostname to IP address translation
  - load distribution
    - replicated Web servers: many IP address correspond to one name

- Distributed database system
  - single point of failure
  - traffic volume
  - distant centralized database

### DDOS attacks

- bombard root servers with traffic
  - not successful to date
  - traffic filtering
  - local DNS servers cache IPs of TLD servers, allowing root server bypass

- bombard TLD servers
  - potentially more dangerous

### Amplification attacks

- exploit DNS for DDOS 

### Pharming attacks

- private data + Farming
  - domain hijacking
  - DNS poisoning: registration of bogus sites

---

## P2P Application

- no always-on server
- Peers are intermittently connected and change IP address

---

## Streaming and CDNS

### video traffic

- major consumer of internet bandwidth
- scalability
  - single mega-video server issues
    1. single point of failure
    2. point of network congestion
    3. long path to distant clients
    4. multiple copies of video sent over outgoing link

### Content Distribution Networks

- Store/serve multiple copies of videos at multiple geographically distributed sites

  

---

---

**[Keyword]**

\- 서버 클라이언트 모델(server/client model): 하나 또는 다수의 중앙 서버에 여러 사용자가 접속하여 서비스와 정보를 제공 받는 모델

\- 피어투피어 모델(peer-to-peer model): 중앙 서버 없이 사용자들이 서로 정보를 공유하는 모델

\- HTTP (HyperText Transfer Protocol): 웹 서버와 사용자 클라이언트(예. 웹 브라우저) 사이에서 웹 문서를 전송하기 위한 규정

\- HTML (HyperText Markup Language): 웹 문서를 작성하기 위한 언어

\- FTP (File Transfer Protocol): 인터넷에서 파일전송을 위한 규정

\- SMTP (Simple Mail Transfer Protocol): 인터넷에서 이메일을 보내기 위한 규정

\- DNS (Domain Name System): 호스트의 도메인 이름을 호스트의 주소로 또는 주소를 도메인 이름으로 변환하는 시스템

\- 캐싱(caching): 빠른 접근을 위해서 데이터(또는 웹 문서)를 일시적으로 특별한 곳(프록시 서버)에 저장하는 기술

\- SSL (Secure Socket Layer): 네스케이프가 만든 TCP/IP 네트웨크에서 암호화 통신을 위한 규정 (TLS 초기 모델)

\- TLS (Transport Layer Security): SSL 3.0 이후 표준화되면서 바뀐 이름이며, TCP/IP 네트워크에서 암호화 통신을 위한 규정

