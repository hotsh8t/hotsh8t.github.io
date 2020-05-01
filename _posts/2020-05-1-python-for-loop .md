---
title: "Python: for loop 사용 완벽정리 "
date: 2020-5-1
categories:
  - DS
tags:
  - Python
  - DS
---

## 꼼꼼맨을 위한 python for 문 정리 
>우선, Python에서 for loop를 돌릴 수 있는 자료료형 중 list, tuple, dict,, series 등에 대해 
>헷갈려 정리 하였다. 추가로, for in range (), for in enumerate() 도 기술하였다. 
1. 숫자형
2. 문자열
3. 리스트
4. 튜플
5. 딕셔너리
6. 집합자료형
7. 불 자료형

Python에서 존재하는 총 변수들은 위 7개이며 각 자료형을 선언하고 'for i in 자료형 :' 을 한 후 print(i)로 찍어보겠다. 

``` python

import networkx as nx
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```
numpy import 를 하고, 

``` python
#1. 숫자형

#2. 문자형

#3. 리스트
list_int =[3, 2, 1]
list_char = ['셋', '둘', '하나']

#4. 튜플
tuple_int = (6, 5, 4)
tuple_char = ('육', '오', '사') 

#5. 딕셔너리
dict = {9 :'구', 8:'팔', 7:'칠'}

```



This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
