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

Community Detection

- The Girvan-Newman algorithm -> link betweenness

- Modularity 어디까지 잘라야 할지 언제 멈춰야 할지?
	- Random한 네트워크는 모듈이 존재하지 않을거라는게 가정
	- Modularity 정량적인 값 제안
	- 모듈러리티는 랜덤하게 연결되어 있는 가능성에 비해 많으냐 적으냐로 판단
	- c1 c2 c3 별로 각각 커뮤니티 별로 Mc(모듈러리티) 계산 각각의 Mc값은 해당 커뮤니티 안에 있는 노드가 얼마나 연결되어 있느냐  Adjacent Aij의 합으로 되어 있는 일종의 density 해당 커뮤니티 안의 링크의 밀도를 계산하게 됨 Pij가 랜덤하게 연결된 차이 차이가 클수록 해당커뮤니티의 빈도 연결에 비해 랜덤한네트워크에 비해 낮으냐 높으냐 판단 가능 
	- 해당 커뮤니티의 랜덤하게 연결하게 연결됢수 있는 가능성에 비해 훨씬 높은빈도로 연결된다면 해당네트워크는 커뮤니티로 잘 찾아낸거임
	- 값이 Pij 랜덤하게 연결된 가능성과 비슷하다면 커뮤니티구조는 일종의 네트워크 구조상에서 잘 찾아낸거라 볼 수 없다. 랜덤한 커뮤니티랑 다를바가 없다 
	- 모듈러리티 값을 각각 구한거를 평균 총합내면 전체내트워크에서 모듈러리티 값 구할 수 있음 
	- 과연 랜덤네트워크와 얼마나 차이가 나는지? 모듈러리티 값이 높을수록 잘 찾아낸거라 볼 수 있다. 
	- 서브옵티멀 파티션 / 옵티말 파티션 0.22 / 0.41?
	- 싱글커뮤니티 / 네거티브모듈러리티 모듈러리티 값이 0 또는 마이너스
- 어떤 시점에서 알고리즘을 멈춰야 하는지?모듈러리티 값을 계속 보면서 
- 링크를 잘라나가면서 확인 -> 몇개의 커뮤니티를 찾아내야 하는지 확인 예시에선 n=3 인경우

- Advanced
	- Overapping communities
	- 여기저기 속할 수 있는 노드 애매한 경우의 노드
- Clique percolation algorithm 어디에 속할것인지? 오버랩하지않고
	- c finder 링크는 오버랩이 없고 노드가 많다 소프트웨어가 있어서 구현 가능
- 오버랩은 노드가 아니라 링크도 오버랩이 가능할수도 있다 하지만 가능성은 적다
패밀리에 관한 링크인지 용도가 분명함 
링크의 커뮤니티구조를 찾으면 오버래핑 을 해결할수 있지 않을까?

링크 커뮤니티 알고리즘
- 링크의 유사도 판단 similarity 해당하는 링크가 얼마나 많은 노드를 공유하고 있는가
- 유사도가 높은 각각의 노드를 잡아서 유사도가 높은 노드를 먼저 붙여나가는 방식
 



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
## Part1 - Building Robustness
## Part2 - Mitigation of malicious attacks
## Part3 - Onion-like topology of robust networks
## Part4 - Halting Cascading Failures
## Part5 - Immunization
## Part6 - Random Immunization
## Part7 - Selective IMmunization
## Part8 - Friendship paradox revisited
## Part9 - Epidemic Prediction
## Part10 - Finding Influential Spreaders
## Part11 - Finding Influential and Susceptible members


## 3) 강의정리<br>

## 4) 실습 및 과제<br>
- 파일Lecture10-Robustness.ipynb파일
- 파일Lecture10-Spreading.ipynb파일
- 파일internet.net파일
- 파일lesmiserables.gml파일






This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
## 동영상Lecture8-bipartite-practice동영상 15:47이수함 
## 동영상Lecture9-community-practice동영상 10:07이수함
