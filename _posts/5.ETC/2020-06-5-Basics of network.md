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
>   네트워크 장비간에 신호를 주고받는 규칙을 정하는 계층, 네트워크 기기간에 데이터를 전송하고 물리주소를 결정한다. 그 규칙들 중 일반적으로 가장 많이 사용하는 규칙이 이더넷  

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
- 랜에 사용되는 네트워크 모델인 이더넷의 물리적인 주소로 컴퓨터 네트워크에서 각각의 기기를 구분하기 위해 사용
- 랜 카드 제조시에 랜카드에 부여된 물리주소로 전세계에서 유일한 번호로 할당됨
- 48비트(6byte) 숫자로 구성 됨
- 예시) **00-23-AE-D9-7A-9A**
    - **00-23-AE**(앞쪽 24비트): 랜카드를 만든 제조사번호
    - **D9-7A-9A**(뒷쪽 24비트) : 제조사가 랜카드에 붙인 일련번호
    
## 데이터링크 계층에서의 캡슐화 : **프레임(+이더넷헤더, + 트레일러)**
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
-  충돌을 방지하기 위해 CSMA/CD 규칙 적용

## 스위치  
- 랜을 구성할 때 사용하는 단말기 간 스위칭 기능이 있는 통신망 중계 장치
- 컴퓨터(호스트)에서 특정한 다른 단말기로 패킷을 보낼 수 있는 기능이 있어 통신효율 향상됨
- 허브와 달리 데이터 충돌이 발생 하지 않음, 데이터링크계층에서 동작, 레이어 2스위치, 스위칭허브
- 스위치내부에는 **MAC주소 테이블(Bridge Table))**이 존재 
- **MAC주소 테이블(Bridge Table))** : **스위치의 포트번호**와 **해당 포트에 연결되어 있는 컴퓨터의 MAC주소**가 등록(매칭)되는 DB
- **MAC 주소 학습기능**  
    - 1)　스위치의 전원을 켠 상태에서는 아직 MAC 주소 테이블에 아무것도 등록되어 있지 않음  
    - 2)　컴퓨터에서 목적지 MAC주소가 추가된 **프레임** 이라는 데이터가 전송되면,  
    - 3)　스위치 내부의 **MAC주소 테이블**을 확인  
    - 4)　출발지 MAC 주소가 등록되어 있지 않으면, MAC 주소를 출발지 포트에 등록(포트에 MAC주소 부여)  
    - 5-1) 목적지 MAC주소가 **MAC 테이블**에 등록되어 있지 않으면, 송신포트 외에 모든 포트에 - 데이터(**프레임**)이 전송됨 -> **플러딩(FLOADING)**  
    - 5-2) **MAC주소 테이블**에 목적지 MAC 주소가 등록되어 있었다면, 목적지 포트(목적지 컴퓨터)에만 데이터가 전송됨 -> **MAC주소 필터링**  

## 전이중통신/반이중통신  
- **전이중통신방식(full-duplex comm.)** : 데이터의 송수신이 **동시에** 이루어지는 통신방식
    - 서로 다른 회선이나 주파수를 사용하기 때문에 데이터를 동시에 전송해도 충돌이 발생하지 않음
    - 컴퓨터를 직접 **랜 케이블(크로스케이블)**로 연결하는 경우, 또는  **스위칭허브**를 사용하는 경우(랜카드와 허브간 동시 송수신 가능)
- **반이중통신방식(full-duplex comm.)** : 회선하나로 송신과 수신을 **번갈아가면서**
    - 데이터를 동시에 전송하면 충돌이 발생
    - **더미허브**(MAC주소테이블이 없는)를 사용하는 경우

## 충돌 도메인(Collision domain)
- 충돌 : 데이터를 한 번에 하나만 전송할 수 있는 채널에 전송 장치 두 개가 같은 시점에 패킷을 보낼때 일어나는 데이터 충돌
- 충돌 도메인 : 충돌이 발생할때 그 영향이 미치는 범위
- 허브(더미허브) : *연결되어 있는 모든 컴퓨터 전체가 하나의 충돌 도메인*이 됨
- 스위치 : 데이터를 동시에 송수신 할 수 있는 전이중통신방식이기때문에 *충돌이 일어나지 않고, 충돌도메인도 해당 포트와 컴퓨터로 한정됨* 

## ARP(Address Resolution Protocol)
- 정의
    - 목적지 컴퓨터의 IP주소를 이용하여 MAC주소를 찾기 위한 프로토콜
    - 네트워크 계층주소와 데이터링크 계층 주소 사이의 변환을 담당하며 **IP주소를 물리주소인 MAC주소로 변환**
    - 이더넷 프레임을 전송하려면 목적지 컴퓨터의 MAC주소를 지정해야 함 
- 절차
    - 출발지 컴퓨터가 목적지 주소를 모르는 경우 MAC 주소를 알아내기위해 네트워크에 브로드캐스트를 한다.-> **ARP요청(Request)**
    - 이 요청에 대해 지정된 IP주소를 갖고 있지 않은 컴퓨터는 응답하지 않고 지정된 IP주소를 가진 컴퓨터는 MAC주소를 응답으로 보냄. -> **ARP응답(reply)**
    - **ARP요청(Request)** 와 **ARP응답(Reply)**를 통해 출발지 컴퓨터는 MAC주소를 얻고 이더넷 프레임을 만들 수 있음 
    - 출발지 컴퓨터는 MAC주소를 얻은 후에 MAC주소와 IP주소의 매핑 정보를 메모리에 보관 ->**ARP테이블(Table)**
    - 이후 데이터 통신은 자신의 컴퓨터에 보관된 **ARP테이블(Table)**을 참고하여 전송
    - 보존기간을 **ARP캐시(Cache)**로 지정하고 일정 시간이 지나면 삭제하고 다시 **ARP요청(Request)**함
    - IP주소가 변경되는 경우 해당 MAC주소도 함께 변경되므로 제대로 통신할 수 없기 때문 
- ARP 
    - **ARP캐시(Cache)** : 가장 최근에 변환한 IP대 하드웨어 주소를 보관하고 있는 RAM의 영역
    - **ARP요청(Request)** :IP주소를 대치할 수 있는 물리주소인 MAC주소를 찾아내기 위해 보내는 브로드캐스트 패킷 요청
    - **ARP응답(Reply)** : ARP요청(Request)에 대한 응답으로 요청한 IP주소에 대한 물리주소인 MAC주소가 실려 있다.

## 이더넷 표준  
- 이더넷규격 10BASE5, 10BASE2, 10BASE-T, 100BASE-T, 1000BASE-T, 10GBASE-T
- 명칭의 정의 예) **10 BASE - T**
    - **10** -> 통신 속도 : 10Mbps
    - **BASE** -> 전송방식 : Baseband( 펄스신호에 의한 디지털 전송방식)
    - **T** -> 케이블종류 : UTP 케이블
    - **-** -> 하이픈(-) 뒤는 케이블의 길이나 케이블의 종류    
    - **5** -> 동축케이블은 케이블의 최대 길이를 100미터 단위로 표시. 즉, 5 인경우 500미터



# 네트워크계층 : 목적지에 데이터 전달하기     
    - 네트워크 계층, IP, IP주소, 네트워크 ID, 서브넷, 라우터  
> **데이터링크 계층**에서는 이더넷 규칙을 기반으로 같은 네트워크에 있는 컴퓨터로는 데이터를 전송(스위칭허브사용)할 수 있지만, 인터넷이나 다른 네트워크로는 데이터 전송 불가. 따라서 **라우터**를 통해 **네트워크 간의 '패킷'통신을 가능**하게 하는 것이 네트워크 계층의 역할

## IP주소와 라우팅
- **IP** : 인터넷에 있는 한 컴퓨터에서 다른 컴퓨터로 데이터를 보내는 데 사용되는 네트워크 계층 프로토콜
- **IP주소** : 네트워크에서도 주소가 있어야 데이터를 송/수신 할 수 있음 
    - IP주소 : '어떤 네트워크'의 '어떤 컴퓨터(장치)'인지를 구분할 수 있도록 하는 주소, 다른네트워크에 있는 목적지를 지정할 수 있음

-  **라우팅** : 네트워크에서 패킷을 목적지로 보낼 때 목적지까지 갈 수 있는 여러가지 경로 중 한가지 경로를 설정    
-  **라우터** :서로 다른 네트워크를 연결해 주는 장치, 데이터의 목적지가 정해지면 해당 목적지까지 어떤 경로로 가능것이 좋은지를 알려주는 기능을 함. **라우팅테이블(rounting table)** 을 통해 경로정보를 등록하고 관리하여 **라우팅(Routing)** 한다.
- **라우팅 테이블** : 컴퓨터 네트워크에서 목적지 주소를 목적지에 도달하기 위한 네트워크 노선으로 변환시킬 목적으로 사용. 다른 네트워크로 가기 위한 가장 좋은 라우터의 정보를 갖고 있다. 

## 네트워크계층에서의 캡슐화(IP헤더) : **IP 패킷**
- 네트워크 계층에는 IP라는 프로토콜을 적용
- 버전, 헤더길이, 서비스유형, 전체패킷길이, ID, 조각상태, 조각의 위치, TTL, 프로토콜, 헤더 체크섬, **출발지IP주소(32bit)**, **목적지IP주소(32bit)**
- IP 프로토콜을 사용하여 캡슐화 할때 IP헤더가 추가된 것을 **IP패킷** 이라고 함
    - [이미지 작성할것]

## IP주소의 구조
- IPv4(32bit, 43억개), IPv6(340조의 1조배의 1조배)
- **공인IP주소** : ISP가 제공, 인터넷에 직접 연결되는 컴퓨터나 라우터에 할당되는 주소
- **사설IP주소** : 회사나 가정의 랜에 있는 컴퓨터에 할당되는 주소
- 랜 안의 여러 컴퓨터에 **IP주소를 할당하는 절차**   
    - 1)　ISP가 제공하는 공인IP주소를 라우터에만 할당  
    - 2-1) LAN 안에 있는 컴퓨터에는 랜의 네트워크 관리자가 자유롭게 사설 IP주소를 할당  
    - 2-2) LAN 안에 있는 컴퓨터에는 **라우터의 DHCP기능**을 사용하여 자동으로 할당   
    **DHCP(Dynamic Host Cofiguration Protocol)** : IP주소를 자동으로 할당하는 프로토콜  
- **네트워크ID** : 어떤 네트워크인지?
- **호스트ID** : 해당 네트워크의 어느 컴퓨터인지?

## IP주소의 클래스 구조  
- 32bit 중에서 **네트워크ID**, **호스트ID**의 크기를 조정하여 클래스를 구분  
    |클래스이름| 내용 | 클래스 이름| 내용|
    |:---:|:---:|:---:|:---:|
    |A클래스 | 대규모 네트워크 주소 | D클래스 | 멀티캐스트(Multicast) |
    |B클래스 | 중형 네트워크 주소 | E클래스 | 연구 및 특수용도 |
    |**C클래스** | **소형 네트워크 주소** | E클래스 | 연구 및 특수용도 |     

- A클래스  
    - **주소범위 : 1.0.0.0 ~ 127.255.255.255**   
        |**네트워크ID**|호스트ID|호스트ID|호스트ID|  
        |:---:|:---:|:---:|:---:|
        |0000001|0000000|00000000|00000000|  
        |~|~|~|~|  
        |01111111|11111111|11111111|11111111|
        |**0~127**|0~255|0~255|0~255|    
    - 공인 IP :1.0.0.0 ~ 9.255.255.255
    - 공인 IP :11.0.0.0 ~ 126.255.255.255
    - **사설 IP :10.0.0.0 ~ 10.255.255.255**

- B클래스
    - **주소범위 : 128.0.0.0 ~ 191.255.255.255**   
        |**네트워크ID**|**네트워크ID**|호스트ID|호스트ID|  
        |:---:|:---:|:---:|:---:|
        |10000000|0000000|00000000|00000000|  
        |~|~|~|~|  
        |10111111|11111111|11111111|11111111|
        |**128~191**|0~255|0~255|0~255|  

    - 공인 IP :128.0.0.0 ~ 172.15.255.255
    - 공인 IP :172.32.0.0 ~ 191.255.255.255
    - **사설 IP :172.16.0.0 ~ 172.31.255.255** 

- C클래스
    - **주소범위 : 192.0.0.0 ~ 223.255.255.255**   
        |**네트워크ID**|**네트워크ID**|**네트워크ID**|호스트ID|  
        |:---:|:---:|:---:|:---:|
        |11000000|0000000|00000000|00000000|  
        |~|~|~|~|  
        |11011111|11111111|11111111|11111111|
        |**192~223**|0~255|0~255|0~255|  
    - 공인 IP :192.0.0.0 ~ 192.167.255.255
    - 공인 IP :192.169.0.0 ~ 223.255.255.255
    - **사설 IP :192.168.0.0 ~ 192.168.255.255**

## 네트워크 주소와 브로드캐스트 주소의 구조  
- 네트워크주소 : 전체 네트워크의 대표 주소(전체 네트워크에서 작은 네트워크를 식별)
    - c클래스 -> 호스트ID가 0 (00000000<sub>2</sub>) 
- 브로드캐스트주소 : 한번에 데이터를 전송
    - c클래스 -> 호스트ID가 255 (11111111<sub>2</sub>)

## 서브넷   
#### 정의   
- **호스트ID로 사용되던 비트를 서브넷 ID로 변경**
- 작은 네트워크로 분할하여 브로드캐스트로 전송되는 패킷의 범위를 좁힘
- A클래스 네트워크와 같은 경우를 예로들면, 호스트ID가 24비트 이기 때문에 브로드캐스트 패킷을 전송하면 모든 컴퓨터에 패킷이 전송되어 네트워크가 정체되기 때문
- **서브넷팅(Subneting)** : 네트워크를 분할 하기 위해 IP주소의 구성을 변경하는 작업
- **서브넷(Subnet)** : 분할된 네트워크
- **서브넷ID** : IP주소의 네트워크 부분을 늘리기 위해 서브넷마스크로 사용되는 비트 (서브넷비트)

#### 서브넷마스크
- IP주소를 서브넷팅 할때 어디까지가 네트워크ID고 어디부터가 호스트ID인지 식별하기 위한 값
- IP주소의 네트워크 부분만 나타나게 하여 같은 네트워크인지를 판별
- A클래스 : 255.0.0.0 /8
- B클래스 : 255.255.0.0 /16
- C클래스 : 255.255.255.0 /24
- Prefix 표시법 : 네트워크ID, 서브넷ID 를 더한값을 표기 예) /28(24+4)

## 라우터
#### 라우터
- 서로 다른 네트워크와 통신을 할 수 있게 해주는 장치
    - 이미지(라우터로 분기할때/스위치로 분기할때)
- 라우터로 네트워크 분리 가능, 스위치로는 불가능(아무리 많은 스위치를 써도 같은 네트워크임)

#### 기본게이트웨이
- 네트워크를 분할한 다음에 컴퓨터 한 대가 다른 네트워크로 접속할 시, **네트워크의 출입구** 설정
- **네트워크의 출입구**를 지정하고 일단은 라우터로 데이터를 전송함
- 컴퓨터는 다른 네트워크로 데이터를 보낼 때 어디로 전송해야하는지 알지 못함
- **기본게이트웨이** : **라우터의 IP주소를 설정 (네트워크의 출입구 설정)**
- '자동으로 IP주소 받기'에 체크되어 있으면 네트워크 외부에 접속할 때 사용되는 기본게이트웨이가 자동으로 설정

#### 라우팅
- 경로정보를 기반으로 현재의 네트워크에서 다른 네트워크로 최적의 경로를 통해 데이터를 전송 
- **라우팅테이블** : 경로정보가 등록되어 있는 테이블
    -이미지(라우팅 테이블에 등록되는 경로정보)
- 라우팅 테이블 등록방법
    - 소규모네트워크 -> 수동으로 등록, 대규모네트워크-> 자동으로 등록
- **라우팅프로토콜**
    - 라우터간에 라우팅 정보를 교환하기 위한 프로토콜
    - RIP, OSPF, BGP 등


# 전송계층 : 신뢰할 수 있는 데이터 전달하기    
    - 전송계층, 연결형 통신, TCP, 일련번호, 포트번호, UDP  
> 목적지에 신뢰할 수 있는 데이터를 전달 : 데이터가 라우터를 경유하는 도중에 패킷이 손상되거나 라우팅 정보가 잘못될 경우 방지. '**역할1 : 오류를 점검하는 기능**', '**역할2 : 어떤 애플리케이션인지 식별**'

## 분류
- 신뢰성/정확성 : 데이터를 목적지에 문제없이 전달 -> **연결형 통신 TCP**
- 효율성 : 데이터를 빠르고 효율적으로 전달(동영상 등) -> **비연결형 통신 UDP**

## TCP
- 신뢰성과 정확성을 우선으로 하는 연결형 통신 프로토콜

## 전송계층에서의 캡슐화1(TCP헤더) : **세그먼트(Segment)**
- **전송계층**에서 **TCP**는 **연결형 통신**에 사용되는 프로토콜, 꼼꼼하게 상대방을 확인하면서 데이터 전송
- **출발지포트번호**, **목적지 포트번호**, 일련번호, 확인응답번호, 헤더길이, 예약영역,  **코드비트**, 윈도우크기, 체크섬, 긴급포인터, 옵션
- TCP 프로토콜을 사용하여 캡슐화 할때 TCP헤더가 추가된 것을 **세그먼트(Segment)** 라고 함
    - [TCP이미지작성할것]
- **연결(Connection)** : 가상의 독점 통신로, TCP통신에서 데이터를 전달하기 위해 사용되는 가상의 통신로  

## **코드비트**
- TCP헤더의 107번째 비트부터 112번째 비트까지 6비트로 연결의 제어정보가 기록 되는 곳  

    |URG|ACK|PSH|RST|SYN|FIN|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|0|0|0|0|0|  
    - SYN : 연결요청
    - ACK : 확인응답
    - FIN : 연결종료

## **3-Way 핸드셰이크**
#### 1. 연결요청        - [이미지]  

1. 연결확립요청 
    |URG|ACK|PSH|RST|*SYN*|FIN|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|0|0|0|**1**|0|  
2. 연결확립응답 + 연결확립요청  
    |URG|*ACK*|PSH|RST|*SYN*|FIN|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|**1**|0|0|**1**|0|  
3. 연결확립응답
    |URG|*ACK*|PSH|RST|SYN|FIN|
    |:---:|:---:|:---:|:---:|:---:|:---:|  
    |0|**1**|0|0|0|0|  
#### 2. 연결종료요청          -[이미지]
1. 연결종료 요청
    |URG|ACK|PSH|RST|SYN|*FIN*|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|0|0|0|0|**1**|  
2. 연결종료 응답
    |URG|*ACK*|PSH|RST|SYN|FIN|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|**1**|0|0|0|0|  
3. 연결종료 요청
    |URG|ACK|PSH|RST|SYN|*FIN*|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|0|0|0|0|**1**|  
4. 연결종료 응답
    |URG|*ACK*|PSH|RST|SYN|FIN|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    |0|**1**|0|0|0|0|  



## 일련번호와 확인응답번호의 구조??
TCP헤더에서의 **일련번호**, **확인응답번호**

#### 일련번호????

#### 확인응답번호????


## 윈도우의 크기(버퍼의 한계크기)??
- 버퍼, 오버플로우 
## UDP
#### 정의    
- 비연결형 통신, 효율성(데이터를 빠르게 보내는 것)을 중요시 함 

## 전송계층에서의 캡슐화2(UDP헤더) : **UDP데이터그램**
- 브로드케스트 가능

## 포트번호
- 전송된 데이터으 목적지가 어떤 애플리케이션 인지 구분  
- 0~1023포트는 주요 프로토콜이 사용하도록 예약(Well know ports)
- 1024 번은 예약되어 있지만 사용되지 않음
- **1025번 이상은 랜덤포트 -> 클라이언트 측의 송신 포트로 사용**
    |애플리케이션|포트번호|
    |:---:|:---:|
    |SSH|22|
    |SMTP|25|
    |DNS|53|
    |HTTP|80|
    |POP3|110|
    |HTTPS|443|   




# 응용계층 : 애플리케이션에 데이터 전송하기   
- 응용계층, WWW, HTTP, DNS서버, SMTP, POP3  
- 이미지 OSI모델계층에서 사용되는 프로토콜과 기술

## WEB SERVER (HTTP)

## DNS

## SMTP / POP3

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





























