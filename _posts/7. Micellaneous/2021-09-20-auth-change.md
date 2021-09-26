---
title: "[mac]권한 열람 및 변경하기"
categories:
  - AUTH
tags:
  - content
  - css
  - edge case
  - lists
  - markup
---

# 맥에서 권한 확인하기

```
ll
```

chmod 755 filename.**


```
#! /bin/bash 
if [ "$1" == "upload" ]
   then aws s3 cp .env s3://mykaistbucket/text-data-analysis/
   else aws s3 cp s3://mykaistbucket/text-data-analysis/.env ./
fi

```

./config.sh upload 명령
