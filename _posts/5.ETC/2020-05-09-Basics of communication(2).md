---
title: "BMC : Basics of Telecommunications(2) "
excerpt: "BCD BASICS(2)" 
date: 2020-05-09
author_profile: false
toc: true
toc_sticky: true
categories:
  - BMC
tag :
  - ETC
---

# BASICS OF Business Data Communication(2)  
 

# [1]. Data Flows with Different Line Configurations  

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


[Transmission Impairments 1](https://youtu.be/rStveoU1xQo)
[Transmission Impairments 2](https://youtu.be/bnl1aKrM62o)


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
    - [RSA Cryptography](https://youtu.be/4zahvcJ9glg)
    - ENcr


## 3. Other Applications of Public/Private Keys  
    - Digital Certificates  
    - Digital Signature  
    - How PGP Works - Encryption  







# [4]. Communication Performance Improvement  


[Race for Faster Communication](https://youtu.be/bub2iCRkyLE)

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
> `compression`과  `multiplexing`이 가장 중요하기때문에 이 두개에 대해서만 언급, 또한 

## 3. Compression 
[Data Compression](https://youtu.be/OtDxDvCpPL4)


- Reduces the size of data files to move more information with fewer bits
    ![Screenshot from 2020-05-16 09-04-35](https://user-images.githubusercontent.com/64456846/82105047-51952f80-9754-11ea-9fd2-6e4389517a78.png)
- Lossless comporession :
    - Based on `code words:` **Huffman codes**
    - Based on `dictionaries:` **Lemple-Ziv**, **Lemple-Ziv-Welch**
    - Lossy :reconstituted data is only `perceptually equialent`(jpeg, mpeg)
    
- Huffman Decoding

## 4. Multiplexing

#### 1) Multiplexing(멀티플렉싱)이란?

- 참고자료 : [Multiplexing(6:07)](https://youtu.be/oYRMYSIVj1o) 
- **Multiplexing** : Simultaneous transmission techonology of **multiple signals across a single data link**.
- **Multiplexer (MUX)** : device that combines several signals into a single signal.
- **Demultiplexer (DEMUX)** : device that performs the inve
rse operation.
- 참고이미지 : **'Direct to Direct'** 와 **'Multiplexing'** 의 비교
    >  Direct to Direct는에 비해 Multiplexing 기술

    ![Multiplexing 의 비교](https://user-images.githubusercontent.com/64456846/83932980-c7cf0400-a7df-11ea-80fd-5086fb3e9529.png)
- Transmission Efficiency(전송효율)
    - Several data sources **share a common transmission medium**, with each source having **its own channel**.
    - Line sharing saves **transmission costs**.
    - Higher data rates mean more **cost-effective** transmissions
    - Most individual data sources require relatively low data rates


#### 2) Multiplexing Technologies(1G-3G)​

- Multiple Access Methods(1G, 2G, 3G)
- 참고이미지 : FDMA, TDMA, CDMA의 비교  
    ![FDMATDMACDMA](https://user-images.githubusercontent.com/64456846/83933161-25b01b80-a7e1-11ea-8196-d00c583cb4d7.png)
    > Frequency는 라디오처럼 터미널마다 각각 다른 주파수 할당, Time, Code 
 
#### 3) **FDM** : Frequency Division Multiplexing 
- FDM이란? 
    > Frequency는 라디오처럼 터미널마다 각각 다른 주파수 할당하는 방식.   
    > 모든 주파수를 더한 것을 커버할만큼의 medium 이 필요함

- **Guard band** to separate channels (no interferences)  
    > 주파수를 합해서 보낼때 겹치는 대역이 생기는데 이를 방지하기 위해 사용하지 않는 대역으로 주파수를 구분해 주는 방법, 제일 낮은 주파수대역에서부터 제일 높은 주파수 대역을 스펙트럼이라 하며 데이터가 전송하는 부분을 Bandwidth 라고함. 이때 Guard band가 더해졌기 때문에 전체 주파수 대역인 Spectrum은 실제 Bandwidth보다 클 수밖에 없음. 

    >고속도로의 차선과 같은 방법으로 Spectrum제한 때문에 채널 확장이 용이하지는 않지만 손쉬운 방법이고, 할당된 Bandwidth를 통해 중단없는 데이터를 보낼 수 있음
- 참고이미지 : Guard band로 인한 Spectrum과 Bandwidth의 관계(**Spectrum > Bandwidth**)   
![Guard band](https://user-images.githubusercontent.com/64456846/83933558-973d9900-a7e4-11ea-9e46-8e7b9bb1e9e9.png)
 

#### 4) **WDM** : Wave-division Multiplexing
- WDM이란?
    > Fiber Optics 즉 광케이블에서는 전자기파장의 일부만 가시광선, 가시광선을 이용한 광케이블, 프리즘을 써서 MUX DEMUX로 활용할 수 있다.  
- 참고이미지 :

    ![WDM](https://user-images.githubusercontent.com/64456846/83933689-cbfe2000-a7e5-11ea-8f97-9da0dfc4caf3.png)

#### 5) **TDM** : Time-Division Multiplexing 
- TDM 이란??
    > 예를들면 시간차를 두고 4개의 디바이스가 순서대로 데이터를 전송하는 방법(시간을 쪼개서 로테이션)

- Synchronous and Statistical TDM
    > Synchronous는 무조건 순서대로 데이터가 들어오는대로 보내기 때문에 비어있는 **frame**이 많아서 데이터 bandwidth에 LOSS가 많다.하지만 어느 터미널에서 데이터가 오는지 분명하게 확인할 수 있어 마킹이 필요 하지 않음. 반면에 statistical TDM은 빈 프레임이 없이 꽉꽉 채워서 보냄 하지만 어떤 터미널에서 오는것인지 슬롯에 마킹을 해줘야 함.

    - ![Synchronous and Statistical TDM](https://user-images.githubusercontent.com/64456846/83934246-65c7cc00-a7ea-11ea-94ff-4b6ddf1db284.png)


- Synchronous TDM and PSTN
    - 끊기지 않아야 하는 경우, 예를들면 서울-부산 사람들의 전화연결을 위해서는 Backbone 에 큰 Line을 두고 Multiplexing 한다. 신뢰할만한 통신네트워크를 묶어서 보증 하는 것-> T1, T3...

Used in the modern digital telephone system 
US, Canada, Japan: DS-0, DS-1 (T-1), DS-3 (T-3), ...
Europe, elsewhere: E-1, E3, ...
Data rate of 1.544Mbps
Uses PCM to digitize voice transmission at 8K/sec, frame
length of 193bits


- SONET: Synchronous Optical Network
    - Specification for high-speed digital transfer via optical fiber
    - Rates from 51.84Mbps to 13.2Gbps
    - Uses Synchronous TDM


#### 6) **CDMA**
- CDMA?
    > QULCOMM 에서 개발, 우리나라에서 제일 먼저 상용화
    - 정의 :
    - 참고자료 : [CDMA](https://youtu.be/oYRMYSIVj1o)
    - CDMA Spread code 가 중요
        - 1/0을 각 채널마다 7bit의 Spread code로 변환하여 신호를 보냄
    - Channel Code  
        - 1 Channel Spreading Code
        - 0 Inversion Spreading 
    - Composite Signal
     - 참고이미지 :

        ![CDMA](https://user-images.githubusercontent.com/64456846/83934171-a410bb80-a7e9-11ea-9429-92b926cb5e34.png)
     

## 5. Segmentation
- Why Do Segmentation? 
    - Error Possibility
    - Reduce Waiting Time on the network
- Tradeoff

#### 7) 5G 참고
- 참고자료.1 : [5G(1)](https://youtu.be/GEx_d0SjvS0)
> 5G 

- 참고자료.2 : [5G(2)](https://youtu.be/LhECDSuXRDs)
> 5G 



> 정리하자면, 통신에서 Peformance를 높이기 위한 3가지 방법으로는,    
> 1.보내는 양을 줄여서 보내는 **compression**    
> 2. 라인을 잘 활용하기 위해 묶어서 보내는 **multiplexing**       
> 3. 라인의 스피드나 에러확률에 따라서 그때그때마다 waiting(queing)타임을 줄이기 위한 **segmentation**  

