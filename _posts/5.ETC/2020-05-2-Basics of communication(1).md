---
title: "BMC : Basics of Telecommunications(1) "
excerpt: "BCD BASICS(1)" 
date: 2020-05-02
author_profile: false
toc: true
toc_sticky: true
categories:
  - BMC
tag :
  - ETC
---


# [1]. Definition and models of Data Communication 

## 1. Data communication?  
- 역원 제도에서부터 발달함, 

## 2. Basic concept and Terminology  
1) Modern Communication Model
- **Human Communication**  
    ```  
    Agent -> Medium -> Agent    
    (Info)   (Signal)  (Info) 
    ```  

- **Telecommunication**  
    ```
    Agent -> DTE/DCE -> Medium -> DCE/DTE -> Agent  
            (S1->S2)             (S2->S1)           
    ```  
    [DTE] : Data Terminal Equipment  
    [DCE] : Data Communication Equipment

2) Farther and Faster
- Analog Communication  
    - 예) (S1, M1) ► (S2, M2),  Telephone  
    - Uses electricity to transmit messages
    - Encoding: sending binaries using signals,  e.g. Inside computers  
- Analog Voice COmmunication
    - Microphone captures voice vibrations, converts them to waves than can be expressed through variations of voltage  
    - Telephone (3000Hz), Hi-Fi Sound (15,000Hz; approximate range of human ear), Compact Disc (20,000Hz for each of two channels)​
- Digital Communication  
    - Digitization: Information → binary representation
    - Digital Convergence : Converting all info into binaries
      Analog(Old info.) + Digitally Capturing -> DIgital information -> Transmission or Storage

## 3. Why Data(Digital) Communication?  
The same technologies for transmission **regardless the kinds of Information**
- **Speed**: Compression​
- **Cost**: Multiplexing (line sharing)	​
- **Reliability(Quality)**: Error detection and correction
- **Security**: Encryption

## 4. Kind (Types) of source information
- Voice​
- Image​
- Video​
- Data (Discrete Symbols)


## 5. Steps for Digital (Data) Communications
- **Input (digitization)**: convert information into  binaries (0 or 1’s)​
- **Encoding**: generate signals(s) of which detectable events represent binaries​
- **Transmission**: sending signals​
- **Decoding**: recovering binaries from shapes of signals​
- **Output**: presenting information to agent  

# [2]. Input (Digitization)  
## 1. Binaries
- DC Calculus 1 : n bits produce 2<sup>n</sup> detectable events
- DC Calculus 2 : to represent x alternatives, n=log<sub>2</sub>x  
- Converting Base Numbers : Deimal(10), Binary(2) and Hexadeciaml(16)
    - Remainder Rule : Decimal to another base
    - Summation Rule : Another base number to decimal
    - Division Rule : Binary to Hexadecimal
    ![Screenshot from 2020-05-16 07-53-36](https://user-images.githubusercontent.com/64456846/82102394-640a6b80-974a-11ea-84cc-abcafad5c1e4.png)

## 2. Text DIgitization
- Binary Conversion from Discrete Symbols​ From Alphanumeric to binaries (Byte)
- ASCII-8bit, EBCDIC(IBM)
- Byte (B), Kilobyte (KB), Megabyte (MB), Gigabyte (GB), Terabyte (TB), Petabyte (PB), Exabyte (EB), Zettabyte (ZB), Yottabyte (YB)

## 3. Audio Digitization
- From Graph(Audio waves)to Coordinates(t1,h1)(t,h2)....
- Converting Samples to Bits
    - Quantizing
        - Similar concept to pixelization in graphic digitization
    - Breaks wave into pieces, assigns a value in a particular range​
    - 8-bit range allows for 256 possible sample levels​
    - More bits means greater detail, fewer bits means less detail​
- Digital Encoding of Voice
    - Primarily used in retransmission devices
        - Uses pulse-code modulation (PCM)
    - The sampling theorem:  S=2F
        -If a signal is sampled at regular intervals of time and at a rate higher than twice the significant signal frequency, the samples contain all the information of the original signal.
    - 8000 samples/sec sufficient for 4000hz
- Sampling Theorem

- Codec

- Digital Voice Communication
## 4. Video Digitization
- Digitazation of Image(Graphics)
- Bitmap
- RGB Addictive Color model & Trichomacy
- Image Quality Issues
- Graphics
- Postscrpt
- Video Communication\
- Example of Video



# [3]. Encoding

## 1. Data, SIgnals, and Transmission
- Digital Data Choices(Analog/Digital transmission)
- Periodic SIgnal Characteristics
- Analog Signaling
- The Electromagnetic Spectrum

## 2. Digital Signal
## 3. Analog Signal
## 4. Bandwidth

## 5. Encoding : Assigning BInaries to Signal
## 6. Modem

## 7. Method of Modulation
- 12. ASK Illustration
- 13. Amplitude Shift Keying(ASK)
- 14. FSK Illustration
- 15. Frequency Shift Keying(FSK)
- 16. PSK Illustration
- 17. DPSK : Differential Phase Shfit Keying
- 18. Complex Modulations
- 19. Digital Encoding Schemes
- 20. NRZ
- 
    - Problme 
    - BIphase ALter
- 21. Manchaster

- Analog Transmission of DIgital Data
    - **FSK :**
    - **PSK :**
    - **DPSK :**
    - **QAM :**
- 23. QAM :Quadrature AMplitude Modulation Illustration
    - CITT
    - CITT V-Series Modem Recommendations

# [4]. Transmission & Media​  
- The physical path between transmitter and reciever
- Design Factors(bandwidth / attenuation / interference / number of receivers)

## 1. Transmission Impairments
- Impairments and Capacity
- Transmission Impairments
    - Attenuation
    - Attenuation Distortion  
    - Delay Distortion
    - Noises
        - Type of Noices :Thermal(White noise), Intermodulation, Crosstalk, Impulse noise
## 2. Two major classes of transmission media
    - Conducted or guided media
    
        - Twisted pair wires : 
            - Two varieties 
                - ST
        
            - Advantages
            - Disadvantages
        - Coax 
            - 
            - Advantages
            - Disadvantages
        - Fiber Optic Cable
            - Fiber optic signals
            -
    - Wireless or unguided media
        - 
        - Directional
            - : 
        - Omnidirectional
            - :
        - Spectrum (United States Frequency Allocations)
        
        - Examples
            - Terrestrial microwave transmission
                - Advantages Disadvantages
                
            - Satellite Microwave Transmission
                - Satellite Transmission Process
    
    
    


