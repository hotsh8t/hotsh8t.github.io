---
title: "BMC : Basics of Telecommunications(3) "
excerpt: "BCD BASICS(3)" 
date: 2020-05-16
author_profile: false
toc: true
toc_sticky: true
categories:
  - BMC
tag :
  - ETC
---

# BASICS OF Business Data Communication(3) :Networks  
 
> Switching Technologies 가 중요하다. 

# [1]. Networks
## 1. Digital Commnication Networks  
- 네트워크의 범위 
    - Distance에 따라 LAN/WAN
    - 컴퓨터 네트워크
    - Wireless
- Terminology
    - Network Components

## 2. Internet
- Structure of the Internet
- Connecting to Internet Backbone
    - 동시 접속자에 dynamic 하게 ip address를 할당
- LIne Contentions

## 3. Networking  

1). Server/Client model  
- Computer networks have opened up an entire frontier in the world of computing called the client/server model​

2). Networking  
- File server : A computer that stores and manages files for multiple users on a network​
- Web server : A computer dedicated to responding to requests (from the browser client) for web pages​
- Node(Host) / Data transfer rate / 

3). Networking Devices  
- Hub
- Switches
- Router
  
## 2. Data Flows  
- **Simplex** : One way only
    - 






# [2]. LAN

## 1. Types of Networks​  
1). 네트워크
- Local-area network (LAN)   A network that connects a relatively small number of machines in a relatively close geographical area​  
- Types (Topology) of LAN​
- 참고자료(수업) : [LAN](https://youtu.be/LCj2HDOd_Mk)

2). 종류 (Various Configuration called toplogies)
- **Ring topology** : A configuration that connects all nodes in a closed loop on which messages travel in one direction

- **Star topology** : A configuration that centers around one node to which all others are connected and through which all messages are sent​

- **Bus topology(Ethernet)** : All nodes are connected to a single communication line that carries messages in both dire*ctions​

## 2. MAC (Medium Access Control)  

- 참고자료(수업) : [Medium Access Control](https://youtu.be/_RdJp4z9I-A)

|Toplogy/MAC| BUS | Tree/Star | Ring|
|---|:---:|:---:|:---:|
|CSMA/CD|O|O||
|Token Bus|O|O||
|Token Ring|||O|  



## 3. CSMA/CD

## 4. Token Bus

## 5. CSMA/CD vs Token Bus  

- 참고이미지 및 링크 : [매체접근방식](http://blog.naver.com/PostView.nhn?blogId=stop2y&logNo=100209824948&parentCategoryNo=&categoryNo=40&viewDate=&isShowPopularPosts=false&from=postView)

    ![CSMA/CD_TOKEN](https://user-images.githubusercontent.com/64456846/83989931-efaa9d00-a982-11ea-90c7-9208108f2512.png)

- 분류 

    |매체접근방식| BUS | Tree/Star | Ring|
    |---|:---:|:---:|:---:|
    |CSMA/CD|O|O||
    |Token Bus|O|O||
    |Token Ring|||O|  

- 특징
    - Under heavy loads, CSMA/CD performs poorly.​
    - Deterministic delay in token bus: important for process control​
    - Priority can be assigned in token bus​
    - Complexity of Token bus​
    - Token bus uses broadband (analog) transmission​


## 6. Token Ring (IEEE 802.5) ​  
> 빈 토큰(빈 패킷)이 미리 돌고 있으면 스테이션에서 아무 것도 없으면 데이터를 로딩해서 보낸다. 전송완료가 되면 마킹을 바꿔서 다른 패킷이 사용 할 수 있다. 순서는 없고 도는 속도가 빨라야지, 빈 패킷기다리는데 오래 걸리면 안되기 때문에 optical 네트워크에서만 이런 방식을 사용함.  

- Token packet circulates when all stations are idle​
- If you want to transmit, wait for a free token​
- Grab free token, transform it into a control field, append to data and send out​
- After round trip, insert a free token​
- Only one data packet at a time.​

## 7. FDDI  (Fiber Distributed Data Interface)​


## 질문사항 : ETHERNET FDDI?

 

# [3]. WAN : Wide-Area Network  

> 와이드 랜에는 몇백만개 오백억개가 넘기 때문에 리스트 만들어서 순서 기다리라고 하는건 불가. 즉 LAN에서 쓰는 방식은 WAN 에서 못씀. 
## 1.​​ Wide-area network (WAN) :

1). WAN이란?

- A network that connects two or more local-area networks over a potentially large geographic distance
- Often one particular node on a LAN is set up to serve as a gateway to handle all communication going between that LAN and other networks
- Communication between networks is called internetworking
- The Internet, as we know it today, is essentially the ultimate wide-area network, spanning the entire globe.
- **Simplex** : One way only
    - 


2). **Who owns the Internet?**
- No single person or company owns the Internet or even controls it entirely. As a wide-area network, it is made up of many smaller networks. These smaller networks are often owned and managed by a person or organization. The Internet, then, is really defined by how connections can be made between these networks.

## 2.​​ Type of networks

## 3.​​ Packet Switching
>  하나의 메시지를 보내는건 너무 양이 많기 때문에 메시지를 패킷단위로 나눠서 보낸다. WAN에서는 스위칭 기술이 네트워크를 연결해 주는 기술이다. 

- To improve the efficiency of transferring information over a shared communication line, messages are divided into fixed-sized, numbered **packets​**  
- Network devices called routers are used to direct packets between networks​
- 참고이미지(수업) :

    ![PACKET](https://user-images.githubusercontent.com/64456846/83988134-562cbc80-a97d-11ea-924a-a2579a2ffb72.png)

## 4.​​ Open Systems
- **Proprietary system :**  A system that uses technologies kept private by a particular commercial vendor​(One system couldn’t communicate with another, leading to the need for​)

- **Interoperability :** The ability of software and hardware on multiple machines and from multiple commercial vendors to communicate​

- **Open systems :**  Systems based on a common model of network architecture and a suite of protocols used in its implementation

## 4.​​ OSI
> OSI는 제품이 아니고 표준 가이드라인임 by ISO 
- OSI  
    |LAYER|DESCRIPTION|
    |:---:|---|
    |7|Application layer|
    |6|Presentation layer|
    |5|Session layer|
    |4|Transport layer|
    |3|Network layer|
    |2|Data link layer|
    |1|Physical layer|

## 5.​ Network Protocls
- Network protocols are layered such that each one relies on the protocols that underlie it. Sometimes referred to as a **protocol stack**
- 참고이미지(수업) : Network Protocols  

    ![Screenshot from 2020-06-08 11-46-13](https://user-images.githubusercontent.com/64456846/83988269-bae81700-a97d-11ea-9b89-7d7fbe9f5e73.png)  

- The International Organization for Standardization (ISO) established the Open Systems Interconnection (OSI) Reference Model​
- Each layer deals with a particular aspect of network communication​


## 5. TCP/IP  
 
- TCP/IP
    - **TCP (Transmission Control Protocol​)** : TCP software breaks messages into packets, hands them off to the IP software for delivery, and then orders and reassembles the packets at their destination​   
    - **IP (Internet Protocol)​** : IP software deals with the routing of packets through the maze of interconnected networks to their final destination​

- TCP/IP Structure

    | Layer | Things to do |
    |---|---|
    | Process (Application) | Telnet, FTP, SMTP|
    |Host-to-Host (TCP,Session) | Reliability and Efficiency, Security |
    | Internet (Transport) | Routing |
    |NAP | Host-Network|

- Networking Protocol :TCP/IP Examples

    ![Protocols](https://user-images.githubusercontent.com/64456846/83989130-66926680-a980-11ea-9808-f5ff45418c86.png)
 

> IP는 길찾기 하는 역할   


## 6. UDP : User Datagram Protocol
- It is an alternative to TCP
-  The main difference is that TCP is highly reliable, at the cost of decreased performance, while UDP is less reliable, but generally faster

## 7.  High-Level Protocols
- Other protocols build on the foundation established by the
TCP/IP protocol suite  
    - **SMTP :** Simple Mail Transfer Protocol
    - **FTP :** File Transfer Protocol
    - **Telnet :**
    - **http :** Hyper Text Transfer Protocol

## 8.**MIME** : Multipurpose Internet Mail Extension​
> 메일은 텍스트로만 되어 있었는데 signature 등이 추가되어서 extension 됨. 네트워크요청시 어떤 request 인지를 specify 해주는게 port 임, Protocol은 단순 그냥 앱이라고 보면 됨 

1). MIME
- Related to the idea of network protocols and standardization is the concept of a file’s MIME type
- Based on a document’s MIME type, an application program can decide how to deal with the data it is given
    - Protocol/Port

2). MIME Type

|Protocol|Port|
|---|---|
|Echo|7|
|File Transfer Protocol(FTP)|21|
|Telnet|23|
|Simple Mail Transfer Protocol(SMTP)|25|
|Domain Name Service(DNS)|53|
|Gopher|70|
|Finger|79|
|Hyper Text Transfer Protocol(HTTP)|80|
|Post Office Protocol(POP3)|110|
|Network News Transfer Protocol(NNTP)|119|
|Internet Relay Chat(IRC)|6667|


 
## 9 Firewalls​
> 들어오는 Request를 보고 판단한다. 네트워크상의 서버인데 보안솔루션 잔뜩 깔려져 있는 서버

- Firewalls​ : A machine and its software that serve as a special gateway to a network, protecting it from inappropriate access

    ​![Firewalls](https://user-images.githubusercontent.com/64456846/83990383-6dbb7380-a984-11ea-95f9-476413ae9cc5.png)

    - Filters the network traffic that comes in, checking the validity of the messages as much as possible and perhaps denying some messages altogether
    - Enforces an organization’s access control policy

## 10. Routing

> tcp/ip이 ip가 라우팅을 하는 것임
- 참고자료(수업) : [Connecting between diffrent protocols](https://youtu.be/1z0ULvg_pW8)

- ![Routing](https://user-images.githubusercontent.com/64456846/83990475-cab72980-a984-11ea-83a8-62d86f2f6881.png)

 



# [4]. Switching Technologies 
> 패킷스위칭은 두가지 방식으로 WLN 데이터그램, 버츄얼서킷방식이 있다. 우리가 매일 쓰는게 버츄얼

- 그림

## 1. Circuit Switching​  
+ **Public Circuit Switched Network** : One way only
    + [그림]
    > 동시 접속자만큼 쓸때마다 롱디스턴스 라인을 연결해줌(자동접속기가) 

    + 
## 3. Datagram 
> 동영상 zoom 같은거는 순서가 제대로 들어오는것이 중요하다. 리셔플링불가



## 4. Virtual Circuit
> 순서가 뒤바뀌지 않게 가는길을 하나로 fix, 1,2,3번은 가는 line만 가기 때문에 순서가 바뀔일은 없다. VPN

## 5. Datagram vs Virtual Circuit
> 
 

# [5]. Internet
## 1. Internet Connections​
+ **Internet backbone**  A set of high-speed networks that carry Internet traffic​
These networks are provided by companies such as AT&T, GTE, and IBM​

+ **Internet service provider (ISP)**  A company that provides other companies or individuals with access to the Internet​

+ **Various technologies available** that you can use to connect a home computer to the Internet​
    - A phone modem converts computer data into an analog audio signal for transfer over a telephone line, and then a modem at the destination converts it back again into data​
    - A digital subscriber line (DSL) uses regular copper phone lines to transfer digital data to and from the phone company’s central office​
    - A cable modem uses the same line that your cable TV signals come in on to transfer the data back and forth​

+ Broadband 

+ Internet 접속 예시 
    - Transaction control protocol/ internet protocol​
    - IP address and domain name server (DNS)​
    - 137.68.237.20  deerlab.Kaist.Ac.Kr​
    - Datagram switching technology​
    - 

+ IP Address

+ Domain Names


## 2.  URL :
> 웹이 나오면서 PORT를 따로 관리 하는게 아니라 Uniform 하게 인터넷상에 붙어있는 모든 컨텐츠를 하나의 방식으로 찾아가는 주소 표준이다. 앞에는 프로토콜이름, 도메인서버이름, 옵셔널포트이름, filepath

- URL identifies a specific resource on a server in a domain​
- URL tells what protocol to use to access the resource​
- URL format:​
    http://deerlab.kaist.ac.kr:1024/program/courses/index.shtml​
    protocol://domain_name[:port] /path_name/file_name​  

## 3. WEB
> 월드 와이드 웹(World Wide Web, WWW, W3)은 인터넷에 연결된 컴퓨터를 통해 사람들이 정보를 공유할 수 있는 전 세계적인 정보 공간을 말한다. 간단히 웹(Web)이라 부르는 경우가 많다. 이 용어는 인터넷과 동의어로 쓰이는 경우가 많으나 엄격히 말해 서로 다른 개념이다. 웹은 전자 메일과 같이 인터넷 상에서 동작하는 하나의 서비스일 뿐이다. 그러나 1993년 이래로 웹은 인터넷 구조의 절대적 위치를 차지하고 있다.

> 인터넷에서 HTTP 프로토콜, 하이퍼텍스트, HTML형식 등을 사용하여 그림과 문자를 교환하는 전송방식을 말하기도 한다.

​- WEB Architecture


## 4. Client/server 

- ![Clientserver](https://user-images.githubusercontent.com/64456846/83992229-89297d00-a98a-11ea-9aa7-17b41b98f592.png)

## 5. HTTP
> HTTP(HyperText Transfer Protocol)는 WWW 상에서 정보를 주고받을 수 있는 프로토콜이다. 주로 HTML 문서를 주고받는 데에 쓰인다. TCP와 UDP를 사용하며, 80번 포트를 사용한다. 

> HTTP는 클라이언트와 서버 사이에 이루어지는 요청/응답(request/response) 프로토콜이다. 예를 들면, 클라이언트인 웹 브라우저가 HTTP를 통하여 서버로부터 웹페이지나 그림 정보를 요청하면, 서버는 이 요청에 응답하여 필요한 정보를 해당 사용자에게 전달하게 된다. 이 정보가 모니터와 같은 출력 장치를 통해 사용자에게 나타나는 것이다.

> HTTP를 통해 전달되는 자료는 http:로 시작하는 URL(인터넷 주소)로 조회할 수 있다.

- Evolution of Computing
- HTTP Protocol
- Web Clients and Servers​
- HTTP Communication​
- Putting it All Together​
- HTTP Is Stateless​
- Location of Web Contents​
- 예시
- Browser​
- Game of Eyeballs​
- Cyber-Identity​

 




# [6]. IoT and LoRa

## 1. Introduction​  
- KEY FEATURES OF THE TECHNOLOGY​
- COVERAGE IN 2017​
- SMART IoT SOLUTIONS – B2B​
    + Environment :
    + Utility :
    + Municipal :
    + Infrastructure​ : 
    + Industry​ :
- Technological comparison of IoT networks in CR​
## 2. Different Wireless Technologies​  
- LoRaWAN Performance(cont.)​
- LoRa Architecture​
- Three classes of End Devices​
- Activation​

## 3. LoRa Technology​  
- Introduction(cont.)
- How it works?
- LoRa modulation
- LoRaWAN network protocol​


+ **Low Power Wide Area Network(LPWAN)​**  
 

