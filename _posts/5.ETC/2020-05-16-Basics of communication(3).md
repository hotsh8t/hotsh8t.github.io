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


## 2. MAC (Medium Access Control)
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
 


# [4]. Switching Technologies 
> 패킷스위칭은 두가지 방식으로 WLN 데이터그램, 버츄얼서킷방식이 있다. 우리가 매일 쓰는게 버츄얼

- 그림

## 1. Circuit Switching​  
+ **Public Circuit Switched Network** : One way only
    + [그림]
    > 동시 접속자만큼 쓸때마다 롱디스턴스 라인을 연결해줌(자동접속기가) 

    + 
## 3. Datagram 

## 4. Virtual Circuit

## 5. Datagram vs Virtual Circuit


됨

# [5]. Internet
## 1. Data Flows  
+ **Simplex** : One way only
    + 

# [6]. IoT and LoRa
## 1. Data Flows  
+ **Simplex** : One way only
    + 


## 1. Data Flows  
+ **Simplex** : One way only
    + 
+ Half Duplex : One way, then the other
    - data may travel in both directions, but only in one direction at a time​data may travel in both directions, but only in one direction at a time​data may travel in both directions, but only in one direction at a time​data may travel in both directions, but only in one direction at a time​data may travel in both directions, but only in one direction at a time​
    - provides non-simultaneous two-way communication​
    - computers use control signals to negotiate when to send and when to receive  
    - the time it takes to switch between sending and receiving is called turnaround time
+ Full Duplex : both ways at the same time

## 2. Transmission Mode  
+ Parallel / Series 모드가 있음
    - 실 사용 예 :
    ![Screenshot from 2020-05-13 19-30-57](https://user-images.githubusercontent.com/64456846/81802135-80db4f00-9550-11ea-9486-49bfd1aa3784.png)
    - parallel :
    - Series :
        * Asynchronous :start/stop bits per unit  
            - Serial communication
        * Synchronous : Block of units

    - Data Link Layer – Managing Data Flow
        OSI LAYER
## 3. Flow Control

# [2]. Communication Impairments  ​  

# [3]. Security of Communication Human Threats to Communications  
- CONFIDENTIALITY, INTEGRITY, NON-REPUDIATION 이 중요하다.   
## 1. Security Control
- Threats

- Security Measures

## 2. Cryptography

- Caesar Ciphers

- Transposition Ciphers

- Cyrptography
    - Cipher
    - Key

- Cryptanalysis

- Encryption & Decryption
    - Encryption on computers 
    - Asymmetric Key Cryptography
    - Symetric/Private Key Encryption


- RSA Cryptography

    - ENcr


## 3. Other Applications of Public/Private Keys  
    - Digital Certificates  
    - Digital Signature  
    - How PGP Works - Encryption  







# [4]. Communication Performance Improvement  

## 1.Performance Measurements
- Transmission Time = (Message Size)/(Channel Capacity)​
- Response Time = MIT + MPT + MOT​
- Waste Time = wait for available links at notes (Queuing Models)​
- E.g., ATM card transactions ​(Asynchronous with parity bit)
    1) Typing your PIN number (think time): 10 characters ​
    2) Sending that information to the machine at the bank: 100 characters​	
    3) Verifying your account and PIN number (application processing): .5 second함
    4) Sending the result to the ATM terminal: 300 characters  where typing speed = 5 characters/second and  modem speed is 100 bps.

## 2. How to improve Efficiency
- Reduce Message Size: **Compression**
- Reduce Waiting Time: **Multiplexing (Line Sharing)​**
- Avoid **Bottleneck**: Segmentation, Intelligent Routing(Packet Switching​), Proxies(Local cache repositories)
- Prepare for Errors: **Optimal Segmentation​**
> `compression`, `multiplexing`이 가장 중요하기때문에 이 두개에 대해서만 언급

## 3. Comporession 
- Reduces the size of data files to move more information with fewer bits
    ![Screenshot from 2020-05-16 09-04-35](https://user-images.githubusercontent.com/64456846/82105047-51952f80-9754-11ea-9fd2-6e4389517a78.png)
- Lossless comporession :
    - Based on `code words:` **Huffman codes**
    - Based on `dictionaries:` **Lemple-Ziv**, **Lemple-Ziv-Welch**
    - Lossy :reconstituted data is only `perceptually equialent`(jpeg, mpeg)
    
- Huffman Decoding

## 4. multiplexing?

