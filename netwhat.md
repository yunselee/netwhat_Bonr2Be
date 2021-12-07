
# 기본질문

internet protocol suite
TCPIP프로토콜 집합계층
5	응용 계층	DNS, TFTP, TLS/SSL, FTP, HTTP, IMAP, IRC, NNTP, POP3, SIP, SMTP, SNMP, SSH, 텔넷, ECHO, 비트토렌트, RTP, PNRP, rlogin, ENRP, …
4	전송 계층	TCP, UDP, DCCP, SCTP, IL, RUDP, …
3	인터넷 계층	IP (IPv4, IPv6)
2.5	ARP	ARP, RARP
1,2	네트워크 인터페이스 계층

- IP 주소란 무엇인지

- Netmask란 무엇인지
1. 넷마스크(Netmask)
네트워크 주소 부분의 비트를 1로 치환한 것이 넷마스크이다.
IP 주소와 넷마스크를 AND연산을 하면 네트워크 주소를 얻을수 있다.

- Netmask를 가진 IP의 Subnet이 무엇인지

- Subnet의 Broadcast 주소란 무엇인지

- Netmask를 가진 IP 주소를 표현하기 위한 여러가지 방법에 무엇이 있을지
CIDR 표기법

- 공인 IP (Public IP) 와 사설 IP (Private IP) 차이점이 무엇인지

- IP 주소의 클래스는 무엇인지

- TCP가 무엇인지

- UDP가 무엇인지

- 네트워크 계층 (Network Layers) 이 무엇인지

- OSI 모델이 무엇인지
7	응용 계층	HTTP, SMTP, SNMP, FTP, 텔넷, SSH & Scp, NFS, RTSP
6	표현 계층	XDR, ASN.1, SMB, AFP
5	세션 계층	TLS, SSL, ISO 8327 / CCITT X.225, RPC, 넷바이오스, 애플토크
4	전송 계층	TCP, UDP, RTP, SCTP, SPX, 애플토크
3	네트워크 계층	IP, ICMP, IGMP, X.25, CLNP, ARP, RARP, BGP, OSPF, RIP, IPX, DDP
2	데이터 링크 계층	이더넷, 토큰링, PPP, HDLC, 프레임 릴레이, ISDN, ATM, 무선랜, FDDI
1	물리 계층
- DHCP 서버와 DHCP 프로토콜이 무엇인지

- DNS 서버와 DNS 프로토콜이 무엇인지

- 두 장치가 IP 주소를 이용하여 통신하기 위한 규칙들에 무엇이 있을지

- 라우팅(Routing) 이 IP와 함께 동작하는 방식

- 라우팅을 위한 기본 게이트웨이가 무엇인지

- IP 관점에서의 포트 (Port) 란 무엇이고, 다른 장치에 연결할 때 어떤 용도로 사용되는지


# 문제


프로토콜
개체간에 이루어지는 데이터 통신을 제어하는 규칙들의 집합
- 구문
- 의미
- 타이밍

OSI모델 (ISO 표준)

네트워크 지원
1. 물리
2. 데이터링크
3. 네트워크
전송
4. 전송
사용자 지원
5. 세션
6. 표현
7. 응용

# ip class

A클래스입니다. 0
0.0.0.0 ~ 127.255.255.255 
1.0.0.0 과 가장 큰 네트워크인 126.0.0.0 
127~은 제외
0xxx xxxx. // xxxx xxxx. xxxx xxxx. xxxx xxxx 
n.h.h.h
B클래스는 반드시 10으로 시작한다
n.n.h.h
네트워크 범위는 10xx xxxx. xxxx xxxx //  xxxx xxxx. xxxx xxxx에서 x들이 가질 수 있는 경우의 수 입니다.  (2^14 개)
호스트 주소 범위는 xxxx xxxx. xxxx xxxx 에서 x들의 경우의 수인 (2^16) - 2 개 입니다. 
(-2 는 네트워크 주소, 브로드캐스트 주소 사용으로 인해 호스트 주소에서 제외해야 합니다.)

 C클래스는 반드시 110으로 시작
 n.n.n.h

 110x xxxx. xxxx xxxx. xxxx xxxx. // xxxx xxxx
192.0.0.0 ~ 223.255.255.255
IP subnetmask

- `Class A` : **10**.0.0.0 ~ **10**.255.255.255
- `Class B` : **172.16**.0.0 ~ **172.31**.255.255
- `Class C` : **192.168**.0.0 ~ **192.168**.255.255

DHCP
응용계층
UDP
ip 동적할당
할당된 IP 주소에 임대 기간을 설정할 수 있다
DHCP는 네트워크 IP 관리 프로토콜인 BOOTP의 대안으로


`Private IP 주소` 대역은 아래와 같다.

private address
- `Public IP 주소`는 전 세계에서 유일한 `IP 주소` 이므로 중복되지 않게 할당된다.
- `Private IP 주소`는 특정한 네트워크 내에서 유일한 `IP 주소`이므로 해당 네트워크 내에서 중복되지 않게 할당된다.
따라서 `**Private IP 주소`는 다른 네트워크 상에선 같은 주소가 존재할 수 있다.**

2.1. 사설IP 주소대역
사설IP 주소는 다음 3가지 주소대역으로 고정된다.

Class A : 10.0.0.0 ~ 10.255.255.255
Class B : 172.16.0.0 ~ 172.31.255.255
Class C : 192.168.0.0 ~ 192.168.255.255



default gateway


클래스 A	    0	8	    24
클래스 B	    10	    16	    16
클래스 C	    110	24	    8
클래스 D (멀티캐스트)	    1110		
클래스 E (예약됨)	    1111


ARP 인터넷 계층 IP 주소를 물리적 네트워크 주소로 대응(bind)

SMTP 응용 계층  인터넷에서 이메일을 보내기 위해 이용되는 프로토콜이다

SNMP 응용계층 간이 망 관리 프로토콜(Simple Network Management Protocol, SNMP) 
IP 네트워크상의 장치로부터 정보를 수집 및 관리하며, 또한 정보를 수정하여 장치의 동작을 변경하는 데에 사용되는 인터넷 표준 프로토콜이다 udp 상에 정의
간이 망관리 

DHCP UDP

네트워크 컴퓨터 위에서 돌아가는 운영체제에서 오류 메시지(Requested service is not available 등)를 전송받는 데 주로 쓰이며

Routing Information Protocol, RIP UDP/IP 상에서 동작하는 라우팅 프로토콜이다
라우팅 프로토콜 : 라우팅 프로토콜(영어: routing protocol)은 라우터 간 통신 방식을 규정하는 통신 규약이다.
네트워크 타임 프로토콜(Network Time Protocol, NTP)은 패킷 교환, 가변 레이턴시 데이터 네트워크를 통해 컴퓨터 시스템 간 시간 동기화를 위한 네트워크 프로토콜이다. udp




There are multiple reasons why TCP wouldn't work for DHCP(v4.)

First of all, TCP is connection-oriented. A TCP connection is defined between two particular hosts. However, when a DHCP client first starts up, it doesn't know which host(s) it wants to talk to. Its only option is to broadcast a DHCP DISCOVER message to all hosts on the local network. Broadcasting is inherently incompatible with TCP's connection-oriented nature, since it's not a 1:1 relationship. Since DHCP is inherently connectionless, UDP makes more sense.

Second, the DHCP client does not have an IP address assigned until the DHCP process is complete. Even if the DHCP client already knew the particular DHCP server it wanted to request an address from (which it typically doesn't) and knew its IP address, it would not be able to open a TCP connection with it because the client doesn't have an IP address yet for the server to respond back to. By the time the client does have an assigned IP address, DHCP's job is already complete.

Third, while not nearly as fundamentally important as the above issues, avoiding TCP also reduces the number of required round-trips by one. A typical DHCP exchange needs two round-trips: DISCOVER (client->server), OFFER (server->client), REQUEST (client->server), and ACK (server->client). Setting up a TCP connection would require an additional round-trip at the beginning for the TCP SYN and SYN-ACK connection setup messages. Data can't be sent on the TCP connection until the final ACK message of the 3-way TCP handshake.



도메인 네임 시스템(Domain Name System, DNS)은 호스트의 도메인 이름을 호스트의 네트워크 주소로 바꾸거나 그 반대의 변환을 수행할 수 있도록 하기 위해 개발되었다



