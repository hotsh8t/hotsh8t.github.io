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
#### 1) Modern Communication Model
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

#### 2) Farther and Faster
- Analog Communication  
    - 예) (S1, M1) ► (S2, M2),  Telephone  
    - Uses electricity to transmit messages
    - Encoding: sending binaries using signals,  e.g. Inside computers  
    
- Digital Communication  
    - Digitization: Information → binary representation
    
    
    
    

## 3. Data(Digital) Communication  
- The same technologies for transmission regardless the kinds of Information
- **Speed**: Compression​
- **Cost**: multiplexing (line sharing)	​
- **Reliability(Quality)**:error detection and correction
- **Security**: Encryption

## 4. Kind (Types) of source information
Voice​

Image​

Video​

Data (Discrete Symbols)


## 5. Steps for Digital (Data) Communications
- **Input (digitization)**: convert information into  binaries (0 or 1’s)​
- **Encoding**: generate signals(s) of which detectable events represent binaries​
- **Transmission**: sending signals​
- **Decoding**: recovering binaries from shapes of signals​
- **Output**: presenting information to agent  

# [2]. Input (Digitization)  
## 1. Binaries
- DC Calculus 1 : n bits produce 2^n detectable events
- DC Calculus 2 : $ (X - \mathbb{E}(X)) \, / \, \sqrt{ \mathrm{Var} (X) } $.  
log<sub>2</sub>x
윗첨자는 `^` string `^`
아랫첨자는 `~` string `~`

## 2. Text DIgitization

## 3. Audio Digitization

- Digital Encoding of Voice

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
    
    
    


