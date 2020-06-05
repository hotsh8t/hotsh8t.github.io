---
title: "BMC : Network for all "
excerpt: "네트워크의 이해_모두의네트워크" 
date: 2020-06-1
author_profile: false
toc: true
toc_sticky: true
categories:
  - BMC
tag :
  - ETC, Network
---

# BASICS OF Network  
**1장.네트워크 첫걸음**  
    - 네트워크, 패킷, 비트와 바이트, 랜(LAN), 웬(WAN), 서버(Server)  
**2장.네트워크의 기본규칙**  
    - 프로토콜, OSI모델, TCP/IP모델, 캡슐화, 역캡슐화, 헤더  
**3장.물리계층 : 데이터를 전기신호로 변환**  
    - 물리계층, 전기신호, 디지털신호, 랜카드, 케이블, 허브  
**4장.데이터링크계층 : 랜에서 데이터 전송하기**  
    - 데이터링크계층, 이더넷, 충돌, MAC주소, 스위치, 전이중 통신방식  
**5장.네트워크계층 : 목적지에 데이터 전달하기**   
    - 네트워크 계층, IP, IP주소, 네트워크 ID, 서브넷, 라우터  
**6장.전송계층 : 신뢰할 수 있는 데이터 전달하기**  
    - 전송계층, 연결형 통신, TCP, 일련번호, 포트번호, UDP  
**7장.응용계층 : 애플리케이션에 데이터 전송하기**  
    - 응용계층, WWW, HTTP, DNS서버, SMTP, POP3  
**8장.네트워크의 전체 흐름**   
    - OSI모델, 헤더, 트레일러, 라우팅, 스위치, 라우터  
**9장.무선 랜의 이해**  
    - 무선랜, 엑세스 포인트, IEEEE80211n, SSO, 채널, 전파간섭  


# 물리계층 : 데이터를 전기신호로 변환  
> OSI모델의 최하위 계층으로, 데이터를 전송하기 위해 시스템 간의 물리적인 연결을 하고 전기신호의 변혼 및 제어하는 역할을 담당한다. 또한 전송매체를 통해 데이터를 통신할 수 있는 전기적인 신호로 바꾸어 전송하는 일을 한다.   

## 랜카드  
    - 0과 1을 전기신호로 변환 -> 네트워크를 통해 데이터를 송수신 할 수 있게 됨  

## 케이블(RJ45)  
    - 커넥터 

## 케이블(UTP/STP)  
    - UTP/STP = 트위스트 페어케이블 = 랜케이블 ...
    - 케이블의 분류 : Cat3, Cat5, Cat5e, Cat6, Cat6a, Cat7

## 케이블(DIRECT/CROSS CABLE)  
    - '1,2', '3,6'이 각각 송신, 수신 인지에 따라 구분
    - 나머지 선 4개는 사용하지 않음
    - DIRECT : 컴퓨터와 스위치 
    - CROSS : 컴퓨터와 컴퓨터(컴퓨터간에 직접 랜 케이블로 연결 할 때, '1,2'->수신, '3,6'->송신)   

## 리피터  
    - 네트워크를 연장하기 위한 장비 
    - 전기신호를 정형(일그러진 전기신호를 복원)하고 증폭하는 기능을 가진 네트워크 중계장비
    - 멀리있는 상대방과 통신할 수 있도록 파형을 정상으로 만드는 기능을 하짐ㄴ 요즘은 허브가 리피터의 기능을 지원

## 허브  
    - **포트(실제로 통신하는 통로)**를 여러개 가지고 있고 **리피터 허브**라고도 불림
    - 리피터는 1:1 통신만 가능하지만 허브는 포트를 여러개 가지고 있음
    - 전기신호를 정형하고 증폭하는 기능
    - 컴퓨터 여러대를 서로 연결하는 장치이기도 함(직접 컴퓨터끼리 연결하지 않아도 통신 가능)
    - 어떤 특정 포트로부터 데이터를 받는다면 해당 포트를 제외한 **나머지 모든 포트로도 받은 데이터를 전송**
    - **더미허브**라고도 부름(*스스로 판단하지 않고 전기신호를 모든 포트로 보내버림*) -> 스위치의 등장  
    - **Auto MDIX** : 다이렉트/크로스 케이블을 자동으로 판단 

# 데이터링크계층 : 랜에서 데이터 전송하기  
>   네트워크 장비간에 신호를 주고받는 규칙을 정하는 계층, 그 규칙들 중 일반적으로 가장 많이 사용하는 규칙이 이더넷  

## 이더넷  
    - 랜에서 적용되는 규칙, 허브와 같은 장비에 연결된 컴퓨터와의 데이터를 주고받을때 사용
    - 같은 허브를 사용하는 랜 환경에서는 모든 포트에 전기 신호가 전달된다 -> 목적지 정보를 추가하여 목적지 이외의 컴퓨터는 데이터를 받더라도 무시

## CSMA/CD  
    - 더미 허브는 들어온 데이터를 그대로 모든 포트에 보내기만 하기 때문에 서로 부딪혀 충돌(collision) 발생
    - 이더넷은 여러 컴퓨터가 동시에 데이터를 전송해도 충돌이 일어나지 않는 구조-> 데이터를 보내는 시점을 늦춤
    - **CSMA/CD** : *Carrier Sense Multiple Access with Collision Detection(반송파 감지 다중 접속 및 충돌 탐지)*
    - **CS** : 데이터를 보내려고 하는 컴퓨터가 케이블에 신호가 흐르고 있는지 아닌지를 확인하는 규칙 
    - **MA** : 케이블에 데이터가 흐르고 있지 않다면 데이터를 보내도 좋다는 규칙
    - **CD** : 충돌이 발생하고 있는지를 확인하는 규칙

## MAC 주소    
    - **MAC** :Media Access Control Address
    - 랜 카드 제조시에 랜카드에 부여된 물리주소로 전세계에서 유일한 번호로 할당됨
    - 48비트(6byte) 숫자로 구성 됨
    - 예시) **00-23-AE-D9-7A-9A**
        - **00-23-AE**(앞쪽 24비트): 랜카드를 만든 제조사번호
        - **D9-7A-9A**(뒷쪽 24비트) : 제조사가 랜카드에 붙인 일련번호
    
## 프레임(+이더넷헤더, + 트레일러)
    - 데이터링크/네트워크에서 이더넷헤더와 트레일러로 캡술화 함 -> 프레임
    - 이더넷헤더(총 14byte) = 목적지MAC주소(6byte) + 출발지MAC주소(6byte) + 유형(2byte)
        - 이더넷 유형(Ethernet type)은 이더넷으로 전송되는 상위 계측 프로토콜
        - : 0800(IPv4), 0806(ARP), 8035(RARP), 814C(SNMP over Ethernet), 86DD(IPv6)
    - 트레일러(FCS : Frame Check Sequence)
        - 데이터 전송 도중에 오류가 발생하는지 확인

## 허브로 연결된 컴퓨터간의 네트워크
    - 예시) A컴퓨터에서 B컴퓨터로 데이터 전송
        - 1) 캡슐화, A컴퓨터의 데이터링크계층에서 데이터에 이더넷헤더와 트레일러를 추가하여 프레임을 만듦 
        - 2) 만들어진 프레임을 물리계층에서 전기신호로 변환(프레임비트열->전기신호)
        - 3) 허브는 컴퓨터 A가 보낸 데이터를 1번 포트로 수신
        - 4) 1번포트로 수신한 데이터를 모든 다른 포트로 전송
        - 5) 3, 4, 5 등 자신의 MAC주소가 프레임내의 목적지 MAC주소와 다른 경우는 데이터 파기
        - 6) 자신의 MAC주소가 프레임 내의 목적지 MAC주소와 동일한 2번포트(컴퓨터B)의 경우만 데이터 수신
        - 7) 물리계층에서 전기신호로 전송된 데이터를 비트열로 변환
        - 8) 역캡슐화, 데이터링크 계층에서 이더넷 헤더와 트레일러를 분리
        - 9) 데이터전송 성공  
    - * 충돌을 방지하기 위해 CSMA/CD 규칙 적용

## 스위치  
    - 허브와 달리 데이터 충돌이 발생 하지 않음, 데이터링크계층에서 동작, 레이어 2스위치, 스위칭허브
    - 스위치내부에는 **MAC주소 테이블(Bridge Table))**이 존재 : 스위치의 포트번호와 해당 포트에 연결되어 있는 컴퓨터의 MAC주소가 등록되는 DB
    - **MAC 주소 학습기능**
        - 1) 스위치의 전원을 켠 상태에서는 아직 MAC 주소 테이블에 아무것도 등록되어 있지 않음
        - 2) 컴퓨터에서 목적지 MAC주소가 추가된 **프레임** 이라는 데이터가 전송되면,
        - 3) 스위치 내부의 **MAC주소 테이블**을 확인
        - 4-1) 출발지 MAC 주소가 등록되어 있지 않으면, MAC 주소를 포트와 함께 등록함



## 충돌 도메인  
 
## 이더넷 표준  


# 네트워크계층 : 목적지에 데이터 전달하기     
    - 네트워크 계층, IP, IP주소, 네트워크 ID, 서브넷, 라우터  
# 전송계층 : 신뢰할 수 있는 데이터 전달하기    
    - 전송계층, 연결형 통신, TCP, 일련번호, 포트번호, UDP  
# 응용계층 : 애플리케이션에 데이터 전송하기   
    - 응용계층, WWW, HTTP, DNS서버, SMTP, POP3  
# 네트워크의 전체 흐름    
    - OSI모델, 헤더, 트레일러, 라우팅, 스위치, 라우터  
# 무선 랜의 이해   
    - 무선랜, 엑세스 포인트, IEEEE80211n, SSO, 채널, 전파간섭  






# [1]. Money History and Theory(What is Money?)  


[History of Money](https://youtu.be/VKOIJS_qZGQ)
 







# [2]. Investment in Blockchain(Bitcoin and Investment)  


The Best Documentary Ever - The Bitcoin Phenomenon
[Blockchain Plainly Explained](https://youtu.be/IMJmd_tNhlM)









# [3]. Introduction to Blockchain  

## 0.Why New Universal Crypto-Currency?  
[Blockchain Expert Explains One Concept in 5 Levels of Difficulty | WIRED](https://youtu.be/hYip_Vuv8J0)

## 1.기본개념
#### (1)용어 
 LEDGER POW 

[Blockchain concept in 5 levels of difficulty](https://youtu.be/hYip_Vuv8J0)

#### (2)비트코인 

#### (3)Byzantine Generals Problem
 
#### (4)PoW

#### (5)Another GPT?




## 2.활용 예
#### (1)비트코인

#### (2)이더리움

#### (3)Different 19 specilized coins


#### (4)Cryptokitties






 
# [4]. Applications of Blockchain    

## 1.Promised Innovations

- Blockchain Opportunities
- Beyond bitcoin
- 
- 


## 2.Tokens and Products
- 3 Types of Tokens

    - **Payment tokens/cryptocurrencies**
tokens which are intended to be used, now or in the future, as a means of
payment for acquiring goods or services or as a means of money or value
transfer. Cryptocurrencies give rise to no claims on their issuer.
    - **Utility tokens**
tokens which are intended to provide access digitally to an application or
service by means of a blockchain-based infrastructure.
    - **Asset tokens**
assets such as a debt or equity claim on the issuer. Asset tokens
promise, for example, a share in future company earnings or future
capital flows. In terms of their economic function, therefore, these
tokens are analogous to equities, bonds or derivatives. Tokens which
enable physical assets to be traded on the blockchain also fall into this
category.
    -![Tokens and Products](https://user-images.githubusercontent.com/64456846/83425898-556dc500-a469-11ea-8d2a-100036bb3be2.png)  


#### (1) Token Economy
 - More generic than traditional money
 - More fungible than traditional money
 - Near zero cost of payment
[Token economy]("https://youtu.be/XatEoU36U-o")
#### (2) Payment and Investment
#### (3) Supply Chain Integrity
#### (4) New Business Models from Blockchains - Edge computing / Digital marketplaces
 



# [5]. Blockchain Industry Trends(Blockchain Project Decision)  

+ What applications on Blockchain?
    - (1) Can this be done without a blockchain? Would this work equally as well if it used cash or existing technology?
    - (2) Is it a big improvement from the existing process?
    - (3) What stakeholders need to be involved for this to work and are they properly incentivized to do so in this system?
    - (4) What's the impetus for this solution to succeed in the market today?  

+ Do you need a blockchain?
    - ![Do you need a blockchain](https://user-images.githubusercontent.com/64456846/83423318-c27f5b80-a465-11ea-98ca-c788b9ef749c.png)  
+ Public or Private
    - ![Public or Private](https://user-images.githubusercontent.com/64456846/83423091-78967580-a465-11ea-9f31-fa8d7c98d873.png)  


+ Blockchain Standard War
    - Hyperledger
    - Ethereum Alliance
    - Ripple Alliance
    - R3
    - Facebook Libra


 



# [6]. Bubble,Bubble and Bubbles(Digital Gold vs. Digital Dollar)  

## 1.


## 2. BUBBLE?

## 3. APPLE?





# [7]. ICO and IEO  
## 1.ICO  
[What is ICO?](https://youtu.be/iyuZ_bCQeIE)


## 2.IEO  
[What is IEO?](https://youtu.be/arFSWUuaA6s)






# [8]. Challenges and Barriers of Blockchain Technology  

## 1.Five common blockchain myths


## 2.Blockchain Pros and Cons


## 3.Cryptocurrencies: Beyond the hype
[Cryptocurrencies: Beyond the hype](https://youtu.be/vo6s1mUjxQQ)


## 4.Cryptocurrency’s biggest threat


## 5. Technical Obstacles, Scalability



# [9]. References





























