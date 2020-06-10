---
title: "SNA : SNMA_Module (2)"
date: 2020-06-08
author_profile: false
toc: true
toc_sticky: true
categories:
  - DS
tags:
  - DS
  - SNA
  - SMNA
---

 
# [8주차 (5/6)] Bipartite and Community<br>
## 1) 강의목록<br>
- 강의콘텐츠Lecture8-bipartite강의콘텐츠
- 강의콘텐츠Lecture9-community강의콘텐츠

## 2) 강의내용<br>
## - Lecture8-bipartite_part1 24:52<br>
1). 사례 
    - business district - business items
    - food ingredients - food recipes 
    - R&D institutions - R&D projects 

2). 정의
- A **bipartite network** is a network whose nodes can be divided into two disjoint sets U and V such that each link connects a U-node to a V-node

3). **Projections** 
- We can generate two projections for each bipartite network.

4). 예시
- **Movie actor network** : nodes corresponds to movies(U), and the other to actors(V)
- **Human disease network** : connects diseases to the genes whose mutations are known to cause or effect the corresponding d
- **Network medicine** :임상실험에서만 발견되었던 현상들을 centrality degree 관점에서 새로운 시각으로 받아들일 수 있다. 
- **COVID-19 예시** : 논문발표됨 (Network Medicine Framework ....)
- **Flavor network** : 문화권 별로 차이를 식재료간의 네트워크로 비교
- **Coexhibition network** : Artist institution 을 참고로 구성


## - Lecture8-bipartite_part2 19:41<br>
1). 모델 구성 관점
- Node/Link 를 구성하는 새로운 방식

2). 추천모델(Matching) Application 관점
  - **Recommendation system** is a subclass of information filtering system that seeks to predict the "rating" or "preference" a user would give to an item. 
  - **Collaborative filtering** : A method of making predictions(filtering) about the interests of a user by collecting preferences or taste information from many users(collaborating).
  - **논문 : Bipartite - Recommendation**

3). **Matching**(매칭) 관점
- In graph theory, a **'matching'** or **'independent edge set'** in a graph is a set of edges without common nodes.
- **논문** : Controllability of complex networks
 

## - Lecture8-bipartite-practice 15:47<br>

## - Lecture9-community_part1 18:23<br>
> small world 네트워크의 구조적인 속성이 이해 됨, 그룹 사이에서의 긴밀한 관계를 통해서 high clustering coefficient 가 구현이 되고 다른 그룹간의 연결을 지어주면서 네트워크 노드 사이에 shortest path를 줄여주는 속성을 두가지를 모두 함께 구현할 수 있는 social network 의 구조적인 속성

- 예시 
    - Belgium - 언어적 이질성, 문화적 차이
    - Zachary's Karate club
- Community?
    - The employees of a company are more likely to interact with their coworkers than withemployees of other companies
    - Circles of friends, or a group of individuals who pursue the same hobby together, or individuals living in the same neighborhood.
- Defining Community
    - A community is a locally dense connected subgraph in a network
        - all members of a community must be reached through other members of the same community
        - nodes that belong to a community have a higher probability to link to the other members of that community thatn to nodes that do not belong to the same community
    - Strong communities
        - A strong communitiy is a connected subgraph whose nodes have more links to other nodes in the same community that to nodes that belong to other communities.

    - Weak communities
        - A weak community si a subgraph whose nodes' total internal degree exceeds their total external degree.
    - The Ravasz algorithm
        - the use of agglomerative hierarchical clustering for community detection
        - DEfine the similarity among nodes

    - Girvan-Newman algorithm
        - Divisive procedures :systematically 

- Modularity
    - Randomly wired networks lack an inherent community structure.
    - Modularity measures the quality of each partition.

- Zero and negative modularity
    


## Lecture9-community_part2 22:56<br>

## Lecture9-community-practice 10:07<br>

## 3) 강의정리<br>

## 4) 실습 및 과제<br>
- 파일Lecture8-bipartite.ipynb파일
- 파일github.csv파일
- 파일Lecture9-community.ipynb파일


## 5) 과제<br>


# [9주차 (5/13)] spreading phenomena 1<br>
## 1) 강의목록<br>
- 강의콘텐츠Lecture10-spreading_phenomena1.pdf강의콘텐츠
- 강의콘텐츠Additional_readings.pdf강의콘텐츠

## 2) 강의내용<br>
## - Lecture10-spreading_phenomena1-part1 13:00<br>
## - Lecture10-spreading_phenomena1-part2 28:36<br>
## - Lecture10-spreading_phenomena1-part3 22:59<br>
## - Lecture10-spreading_phenomena1-part4 10:57<br>
## - Lecture10-spreading_phenomena1-part5 16:02<br>
## - Lecture10-spreading_phenomena1-part6 19:29<br>

## 3) 강의정리<br>

## 4) 실습 및 과제<br>
- 파일Additional_readings.zip파일

# [10주차 (5/20)] spreading phenomena 2 (Robustness & Spreading)<br>
## 1) 강의목록<br>
- 강의콘텐츠Lecture11-spreading_phenomena2.pdf강의콘텐츠

## 2) 강의내용<br>
## - week10-spreading_phenomena2 02:59:54<br>

## 3) 강의정리<br>

## 4) 실습 및 과제<br>
- 파일Lecture10-Robustness.ipynb파일
- 파일Lecture10-Spreading.ipynb파일
- 파일internet.net파일
- 파일lesmiserables.gml파일






This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
## 동영상Lecture8-bipartite-practice동영상 15:47이수함 
## 동영상Lecture9-community-practice동영상 10:07이수함