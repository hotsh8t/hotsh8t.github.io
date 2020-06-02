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
Multiplexing Technologies(1G-3G)​
1) types
- Frequency Division Multiplexing (FDM)​
- Guard Band in FDM​
- Wave-division Multiplexing (WDM)​
- Time-Division Multiplexing (TDM)​


- CDMA Spread code 가 중요








