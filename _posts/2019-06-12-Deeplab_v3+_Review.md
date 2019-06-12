---
layout: post
comments: true
title:  "Deeplab v3+ 논문 리뷰"
date:   2019-06-12
author: "kmss1258"
categories: Posts
cover: "/assets/post-assets/2017-09-24-what-should-I-develop/cover.jpg"
---

# Deeplab v3+ 논문 리뷰    
Reference : https://medium.com/hyunjulie/    


# DeepLab V3+ 설명
Deeplab V3+ 는 이전 버전인 DeepLab V3에서 개선된 형태의 네트워크 구조이다.    
해당 네트워크는 인코더 / 디코더 부분으로 나뉘어져 있다.    
인코더 부분에서는 DeepLab V3와 변형된 Xception을 인코더로 채택 하고 있으며 컨볼루션을 진행 할 때 다른 네트워크와는 다른 Atrous Convolution,을 진행한다.    
디코더 부분에서는 인코더 과정의 네트워크 출력값과 인코더 전체 출력값을 concatenate 하여 디코딩을 진행한다.

# Atrous Convolution
Atrous Convolution은 기존 Convolution과 달리 지정한 간격 만큼 띄어 이미지를 컨볼루션 하는 과정이다. 상세 그림은 아래와 같다.    

# Spatial Pyramid Pooling
Spatial Pyramid Pooling은 DeepLab V3에 존재하는 네트워크 구조이다.    
제안 방법은 아래와 같이 동일한 입력 값을 서로 다른 Grid Scale에서 Pooling을 진행하여 마지막에 특징 맵을 concatenate 시키는 형태이다.

# Depthwise Separable Convolution
이는 모델의 성능은 유지하면서 계산 비용과 Weight 수를 줄일 수 있는 방법이다. 해당 방법은 동일한 입력 값을 Point/Depth/Channel 동시에 컨볼루션 하는 방법이 아닌, Depth/Channel와 Point 별 Convolution 연산을 따로 진행하는 방법이다. 자세한 설명은 아래 그림과 같다.
