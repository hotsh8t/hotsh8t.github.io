---
title: "Seaborn: barplot오류 for꼼꼼맨  "
date: 2020-531
categories:
  - Python
---

## 꼼꼼맨을 류위한 sns.barplot 오류 정리  
>sns.barplot(data= 데이터프레임, x= 데이터프레임 컬럼값x, y=데이터프레임 컬럼값y)으로 써야함
>group_by 매써드를 쓰면 dataframe 형에서 series 형으로 바뀌게 된다.
>또한 group_by 하면 내가 x값으로 쓰고싶은 내용이 index가 되는데, index값은 barplot의 x값으로 못씀  
>따라서 group_by 할때 reset_index() 사용하여 index를 한 층 더 만들어주면 sns.barplot 사용 가능


``` python
mean_by_region = df_covid.groupby('region').total_cases.mean().reset_index()
sns.barplot(data=mean_by_region, x='region', y='total_cases')

```


This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
