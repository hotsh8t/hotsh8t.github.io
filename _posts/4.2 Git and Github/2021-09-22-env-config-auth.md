---
title: "[env]git commit 시 비밀번호 관리하기"
toc: true
toc_sticky: true
categories:
  - GIT
tags:
  - content
  - css
  - edge case
  - lists
  - markup

---
---
# GIT commit 시 비밀번호 관리하기
 *git repository를 public으로 관리하는 경우 비밀번호가 공개될 위험이 있다. 이러한 경우 어떻게 해결할 수 있는지 확인해보자. 
 먼저 비밀번호와 관련된 파일은 .env 라는 별도 파일에 내용을 저장한 후 이 내용을 소스단에서 불러와 사용하는것으로 수정해야 함 
.env로 설정파일을 가져오기 위해서는 매크로로 저장된 것처럼 가져 오기 위해서는 os.getenv("정의한 내용"), 예를들면 ELASTIC_SEARCH_URL = os.getenv("ELASTIC_SEARCH_URL") 과 같이 사용할 수 있음
os.getenv함수를 쓰기 위해서는 상단에 load_dotenv(), 그리고 이를 위해서는 from dotenv import load_dotenv 필요

## 1. 기존 파일에서 어떤 부분을 비공개로 할지 판단
## 2. 비공개로 하고 싶은 부분을 config.py 파일을 생성하여 추가

  ``` python

  import os
  from dotenv import load_dotenv

  load_dotenv()

  ELASTIC_SEARCH_URL= 'https://******************.es.amazonaws.com'
  ELASTIC_SEARCH_ID= '*****'
  ELASTIC_SEARCH_PW= '**************'
  ELASTIC_SEARCH_AUTH= (ELASTIC_SEARCH_ID, ELASTIC_SEARCH_PW)

  ```
  위와 같이 작성 후

## 3. config.py 파일이 잘 불러와지는 지 확인 
  
  ``` python
  from config import * # import config file 
  ```
  정의한 내용을 사용하고 싶은 파일에 위와 같이 선언 해 준다. 

## 4. 정상동작 확인 

## 5. config.py 파일에서 비공개내역 .env 파일을 만들어서 추가(마치 매크로 선언처럼)

## 6. 원본 파일의 비공개내역을 os.getenv 로 변경 


``` python

import os
from dotenv import load_dotenv

load_dotenv()

ELASTIC_SEARCH_URL = os.getenv("ELASTIC_SEARCH_URL")
ELASTIC_SEARCH_ID = os.getenv("ELASTIC_SEARCH_ID")
ELASTIC_SEARCH_PW = os.getenv("ELASTIC_SEARCH_PW")
ELASTIC_SEARCH_AUTH = (ELASTIC_SEARCH_ID, ELASTIC_SEARCH_PW)

```


## 7. .env는 github 에 올릴때 제외하도록 설정

- os.getenv를 통해 변수 접근하는 방법 설명

# dotenv 설치
- pip install python-dotenv 설치

# .env를 만들고 from dotenv import load_dotenv로 함

# .env는 github 에 올릴때 제외
