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
## 1. Digital COmmnication Networks  
+ 네트워크의 범위 
    + Distance에 따라 LAN/WAN
    + 컴퓨터 네트워크
    + Wireless
+ Terminology
    + Network Components

## 2. Internet
+ Structure of the Internet
+ Connecting to Internet Backbone
    - 동시 접속자에 dynamic 하게 ip address를 할당
+ LIne Contentions

+ Networking
    + Networking Devices

  
## 2. Data Flows  
+ **Simplex** : One way only
    + 






# [2]. LAN

## 1. Types of Networks​  
+ Local-area network (LAN)   A network that connects a relatively small number of machines in a relatively close geographical area​  
+ Types (Topology) of LAN​
[LAN](https://youtu.be/LCj2HDOd_Mk)


## 2. MAC (Medium Access Control)
[Medium Access Control](https://youtu.be/_RdJp4z9I-A)
## 3. CSMA/CD

## 4. Token Bus

## 5. CSMA/CD vs Token Bus  
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


## 질문사항 : ethernet fddi?


 

# [3]. WAN
> 와이드 랜에는 몇백만개 오백억개가 넘기 때문에 리스트 만들어서 순서 기다리라고 하는건 불가. 즉 LAN에서 쓰는 방식은 WAN 에서 못씀. 
## 1.​​ Wide-area network (WAN) :A network that connects two or more local-area networks over a potentially large geographic distance
+ **Simplex** : One way only
    + 

## 2.​​ Type of networks

## 3.​​ Packet Switching
>  하나의 메시지를 보내는건 너무 양이 많기 때문에 메시지를 패킷단위로 나눠서 보낸다. WAN에서는 스위칭 기술이 네트워크를 연결해 주는 기술이다. 

- To improve the efficiency of transferring information over a shared communication line, messages are divided into fixed-sized, numbered **packets​**  
- Network devices called routers are used to direct packets between networks​
- 그림

## 4.​​ Open Systems
- **Proprietary system :**  A system that uses technologies kept private by a particular commercial vendor​(One system couldn’t communicate with another, leading to the need for​)

- **Interoperability :** The ability of software and hardware on multiple machines and from multiple commercial vendors to communicate​

- **Open systems :**  Systems based on a common model of network architecture and a suite of protocols used in its implementation

## 4.​​ Open Systems : OSI(
> OSI는 제품이 아니고 표준 가이드라인임 by ISO 

- The International Organization for Standardization (ISO) established the Open Systems Interconnection (OSI) Reference Model​
- Each layer deals with a particular aspect of network communication​


## 5. TCP/IP 
- TCP/IP Structure
`
Layer		        Things to do
Process (Application)	Telnet, FTP, SMTP
Internet (Transport)    Reliability and Efficiency, Security
NAP    			Host-Network
`

- TCP/IP Examples


- Networking Protocol :TCP/IP 

> IP는 길찾기 하는 역할   

- TCP/IP
    - **TCP stands for Transmission Control Protocol​** : TCP software breaks messages into packets, hands them off to the IP software for delivery, and then orders and reassembles the packets at their destination​   
    - **IP stands for Internet Protocol​** : IP software deals with the routing of packets through the maze of interconnected networks to their final destination​

## 6.  High-Level Protocols
    - **SMTP :**
    - **FTP :**
    - **Telnet :**
    - **http :** 

## 7.**MIME Types** : Multipurpose Internet Mail Extension​
> 메일은 텍스트로만 되어 있었는데 signature 등이 추가되어서 extension 됨. 네트워크요청시 어떤 request 인지를 specify 해주는게 port 임, Protocol은 단순 그냥 앱이라고 보면 됨 

    - Protocol/Port

## 8 Firewalls​
> 들어오는 Request를 보고 판단한다. 네트워크상의 서버인데 보안솔루션 잔뜩 깔려져 있는 서버


## 9. Routing
> tcp/ip이 ip가 라우팅을 하는 것임

-
 

[Connecting between diffrent protocols](https://youtu.be/1z0ULvg_pW8)

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
​
## 4. Client/server 

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
 
