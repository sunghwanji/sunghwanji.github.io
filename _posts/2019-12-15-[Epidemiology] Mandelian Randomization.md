---
title : "[Epidemiology] Mendelian Randomization"
tags:
  - Epidemiology
use_math: false
---

굉장히 흥미로운 연구방법이 있어서 공유  
[링크](https://www.youtube.com/watch?v=LXsrJg9shsI&feature=youtu.be)   
  
### Mendelian Randomization
의학연구자들들은 causation에 관심이 많다. A(exposure)가 B(outcome)라는 질병을 일으킨다면, A를 조절하면 B를 예방할 수 있기 때문이다.  
근데, A(exposure)와 B(outcome) 모두에 영향을 미치는 C라는 변수(역학적으로는 교란변수(confounder)라고 한다.)가 있다면 C의 영향을 보정해줘야한다.
  
![사진](http://jungfrau.co.kr/fileUp/bbs/MR3.jpg)
예를 들어, 위의 동영상의 예시 처럼, Vit B level이 낮은 것이 골절(fracture)을 일으킨다고 가설을 세우자. 그리고 그것을 증명하기 위해 Vit B level이 낮은사람을 쭉 추적해봤더니 실제로 골절이 많이 생겼다고 하자. 그러나 이것만 가지고는 low Vit B level과 fracutre risk의 association을 본것이지 causation을 본 것이 아니다.   
![사진](http://jungfrau.co.kr/fileUp/bbs/MR2.jpg)
excercise라는 교란변수를 생각해볼 수 있다. 운동을 적게하는것 자체가 햇빛 노출을 적게함으로서 Vit D level을 낮추는 동시에, 운동을 적게하는것 자체가 골절의 위험을 높일 수 있기 때문이다.  
이런 교란변수의 존재가 observational study(연구자의 개입이 없는)의 가장 큰 약점이라고 할 수 있다.  
  
의학연구자들은 이 교란변수를 보정하기 위해 수 없이 많은 노력을 하지만, 결국에 어떤 것도 완벽하지는 않다.  
  
결국 Random하게 두 집단을 나누고 연구자가 적극적으로 개입하는 Randomized Controlled Trial(RCT)이 강력할 수 밖에 없는 이유다. 이론적으로는 두 집단을 무작위로 나눈다면 confounder도 무작위로 나뉠 것이고 exposure of interest의 영향만 볼 수 있기 때문이다.  
  
그러나 RCT는 비싸고, 오래걸리고, 윤리적인 문제(예를들어 담배의 영향을 보고싶을 때 특정 집단에 강제로 담배를 피우게 할 수는 없다.)가 있다.  
  
Mendelian Randomization(MR)은 굉장히 재밌는 방법으로 이 문제를 해결한다.  
  
![사진](http://jungfrau.co.kr/fileUp/bbs/MR.jpg)
예를들어 Vit D level을 결정하는 유전자가 있다면? 혹은 그런 경향을 갖게하는(predispose) 유전자가 있다면?    
그런 유전자를 갖는 것은 순전히 random하다. 즉, 환경과 전혀 무관한 우연한 일이다.  
그럼 만약, low Vit D가 골절위험을 올린다면, 그 유전자를 가진 사람도 걸절위험이 높아야 한다.  
만약, low Vit D 와 높은골절위험의 association이 excercise같은 다른 교란변수들에 의한 것이라면 그 유전자와 골절위험은 무관할 것이다.  
  
굉장히 기발한 방법이다 !!!!
  
### Assessment of the genetic and clinical determinants of fracture risk: genome wide association and mendelian randomisation study
[링크](https://www.bmj.com/content/362/bmj.k3225)  
Mendelian Randomization이 적용된 저널이며, 그 이외에도 수 많은 통계학적, 역학적인 고민이 들어가 보이는 연구가 있다. 아직 내공이 부족하여, 100% 이해하지는 못했지만...  

이 연구는 Vit D level 뿐만 아니라 지금까지 골절과 '연관(association)'(그러나 원인인지는 모르는)이 있다고 알려진 골밀도, 폐경나이, 류마티스관절염 등 총 14개지를 지금까지 이뤄진 GWAS study를 토대로 MR을 적용했다. 결과는 14개의 인자 중 1개, 골밀도만 strong evidence of causality가 있었고, 쥐는 힘이 weak evidence of causality가 있었다. 결국 이 연구는 나머지 골절과 연관이 있다고 알려진 12개 인자 중 2개만이 인과관계가 있다고 주장하고 있고, 골절을 줄이려고 한다면 그 두가지에 개입을 해야 한다고 주장한다.  
  
즉, 폐경이 이른사람은 골절의 위험도가 높지만, 그 사람의 폐경을 인위적으로 미룬다고 해서 골절의 위험이 낮아지지는 않을 것라는 것이다. 우리가 골절을 예방하기 위해 Vit D를 먹지만, 그게 실제로 골절을 줄이지는 않을 것이라는 것이다.



### 감상
1. RCT는 evidence pyramid의 꼭지점에 있는, 굉장히 강력하며, 현대의학의 근간이 되는 연구방법이다. 그러나 비판점도 분명히 존재한다고 생각한다. 잠깐 생각해봐도, 비싸고, 오래걸린다. N수가 충분히 있어야 한다. 무엇보다 개인간의 다양성을 잘 인정하지 않는 연구방법이라고 생각한다.
  
그냥 막연히 RCT가 최고의 연구 방법일까, 다른 방법은 없을까, 에 대한 고민을 해본 적은 있는데, 이런 기발한 방법을 보고 매우 반가웠다.  
  
2. 위에서 언급한 논문을 읽으면서 (100% 이해하지는 못했지만) 여러 독립적으로 모인 코호트를 분석한, 다양한 전문가의 고민이 굉장히 많이 들어간 연구라는 생각이 들었다. 언젠가는...저런 연구를 해보고 싶다 ㅎㅎ
