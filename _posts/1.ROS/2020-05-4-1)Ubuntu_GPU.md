
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


### apt-ache search nvidia  
- 설치 할 수 있는 NVIDIA 그래픽카드 드라이버의 리스트르 보여준다. 


.1 catkin tools 설치
* catkin_tools의 설치 안내 [페이지](https://catkin-tools.readthedocs.io/en/latest/installing.html)

``` python
>sudo apt-get install python-catkin-tools
```


### 1.2 catkin_ws 폴더 생성
``` python
>mkdir -p ~/catkin_ws/src

```


### 1.3 catkin_ws 초기화
* 반드시 catkin_ws 폴더에서 catkin init 를 해야 한다. 

``` python
>cd catkin_ws
>cd catkin init
```

 
This post is based on [pinkwink](https://github.com/PinkWink) and [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)
