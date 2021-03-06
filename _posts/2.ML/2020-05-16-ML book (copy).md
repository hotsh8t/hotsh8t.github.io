---
title: "ML : MLMLMLML "
excerpt: "머신러닝 알고리즘 총 정리 by 머신러닝 도감 " 
date: 9999-12-31
author_profile: false
toc: true
toc_sticky: true
categories:
  - ML
tags:
  - DL
  - ML
---
> 이 포스팅은 인공지능시리즈21 머신러닝도감을 참고하여 작성되었습니다. 

TEST




# 0. 시작전에
====
# 0-1 평가방법
# 0-2 데이터처리


# 1. 지도학습
====
# 1-1 선형 회귀
# 1-2 정규화
# 1-3 로지스틱 회귀
# 1-4 서포트 벡터 머신
# 1-5 서포트 벡터 머신(커널 기법)
# 1-6 나이브 베이즈 분류
# 1-7 랜덤 포레스트
# 1-8 신경망
# 1-9 kNN(k-최근접 이웃 알고리즘)


# 2.비지도학습
====
# 2-1 PCA(주성분 분석)  
# 2-2 LSA(잠재 의미 분석)  
# 2-3 NMF(음수 미포함 행렬 분해)  
# 2-4 LDA(잠재 디리클레 할당)  
# 2-5 k-means(k-평균 알고리즘)  
# 2-6 가우시안 혼합 모델  
# 2-7 LLE(국소 선형 임베딩)  
# 2-8 t-SNE(t-분포 확률적 임베딩)  

----


A notice displays information that explains nearby content. Often used to call attention to a particular detail.

When using Kramdown `{: .notice}` can be added after a sentence to assign the `.notice` to the `<p></p>` element. 

**Changes in Service:** We just updated our [privacy policy](#) here to better service our customers. We recommend reviewing the changes.
{: .notice}

**Primary Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. [Praesent libero](#). Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--primary}

<div class="notice--primary" markdown="1">
**Primary Notice with code block:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. [Praesent libero](#). Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.

```html
<html>
  <body>Some body.<body>
</html>
```
</div>

**Info Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing elit](#). Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--info}

**Warning Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. [Integer nec odio](#). Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--warning}

**Danger Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing](#) elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--danger}

**Success Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at [nibh elementum](#) imperdiet.
{: .notice--success}

Want to wrap several paragraphs or other elements in a notice? Using Liquid to capture the content and then filter it with `markdownify` is a good way to go.

```html
{% raw %}{% capture notice-2 %}
#### New Site Features

* You can now have cover images on blog pages
* Drafts will now auto-save while writing
{% endcapture %}{% endraw %}

<div class="notice">{% raw %}{{ notice-2 | markdownify }}{% endraw %}</div>
```

{% capture notice-2 %}
#### New Site Features

* You can now have cover images on blog pages
* Drafts will now auto-save while writing
{% endcapture %}

<div class="notice">
  {{ notice-2 | markdownify }}
</div>

Or you could skip the capture and stick with straight HTML.

```html
<div class="notice">
  <h4>Message</h4>
  <p>A basic message.</p>
</div>
```

<div class="notice">
  <h4>Message</h4>
  <p>A basic message.</p>
</div>

/home/wia/download/hotsh8t.github.io/_posts/3.DS/2020-05-12-Social Network Analysis.md
This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
