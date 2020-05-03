
---
title: "Ubuntu : NVIDIA GPU 드라이버 설치 "
excerpt: "NVIDIA 드라이버 확인 및 설치 " 
date: 9999-12-31
categories:
  - ROS
tag :
  - ROS, catkin
---

#  NVIDIA GPU 확인방법

### 그래픽 카드 확인 1  
```c
$ sudo lshw -C display
```
실행결과
```
AILAB@AILAB:~$ lshw -C display
WARNING: you should run this program as super-user.
  *-display                 
       description: VGA compatible controller
       product: Mars [Radeon HD 8730M]
       vendor: Advanced Micro Devices, Inc. [AMD/ATI]
       physical id: 0
```

### 그래픽 카드 확인 2
```c
$ lspci | grep -i VGA
```
실행 결과 
 1f11(rev a1)사양은 RTX 2060
```
AILAB@AILAB:~$ lspci | grep -i VGA
00:02.0 VGA compatible controller: Intel Corporation 4th Gen Core Processor Integrated Graphics Controller (rev 06)
01:00.0 VGA compatible controller: NVIDIA Corporation Device 1f11 (rev a1)
```
### 그래픽 카드 확인 2
```c
$ lspci -k
```
결과  
```
VGA compatible controller: NVIDIA Corporation Device 1f11 (rev a1)
```


### 그래픽카드 설치 여부 확인
```c
cat/proc/driver/nvidia/version
```
결과 :  NVIDIA 미설치시
```
cat:/proc/driver/nvidia/version:No such file or directory
```




### nouveau 설치 확인 및 제거
아래 명령어 실행 후 1줄 이상 출력되면 nouveau 가 설치된 환경이다. NVIDIA 정식 드라이버 설치를 위해 삭제 필요 

```C
$ lsmod | grep nouveau
```



### apt-ache search nvidia  
- 설치 할 수 있는 NVIDIA 그래픽카드 드라이버의 리스트르 보여준다. 


[제일 잘 설명된 사이트](https://smprlab.tistory.com/29)






 
This post is based on [pinkwink](https://github.com/PinkWink) and [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)
