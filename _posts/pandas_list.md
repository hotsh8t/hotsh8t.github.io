---
title:  "list 값 얻어오"
excerpt: "list 값 얻어오는 방법 정"

categories:기
  - Blog
tags:
  - Blog
last_modified_at: 2019-04-13T08:06:00-05:00
---
list 값 얻어오는 방법은
list(dataframe) 해도 되고, 
# your code here
mean_total_cases_by_region = df_covid.groupby('region').total_cases.mean()
mean_total_cases_by_region
x = mean_total_cases_by_region.index.tolist()
y = mean_total_cases_by_region.values.tolist()

x1 = list(mean_total_cases_by_region.index)
y1 = list(mean_total_cases_by_region.values)

print(type(x), y, type(x1), y1)

이 글의 제목은 {{ page.title }}이고
마지막으로 수정된 시간은 {{ page.last_modified_at }}이다.
