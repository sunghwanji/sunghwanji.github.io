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

예를 들어, 위의 동영상의 예시 처럼, Vit B level이 낮은 것이 골절(fracture)을 일으킨다고 가설을 세우자. 그리고 그것을 증명하기 위해 Vit B level이 낮은사람을 쭉 추적해봤더니 실제로 골절이 많이 생겼다고 하자. 그러나 이것만 가지고는 low Vit B level과 fracutre risk의 association을 본것이지 causation을 본 것이 아니다.  
excercise라는 교란변수를 생각해볼 수 있다. 운동을 적게하는것 자체가 햇빛 노출을 적게함으로서 Vit D level을 낮추는 동시에, 운동을 적게하는것 자체가 골절의 위험을 높일 수 있기 때문이다.  
이런 교란변수의 존재가 observational study(연구자의 개입이 없는)의 가장 큰 약점이라고 할 수 있다.  
  
의학연구자들은 이 교란변수를 보정하기 위해 수 없이 많은 노력을 하지만, 결국에 어떤 것도 완벽하지는 않다.  
  
결국 Random하게 두 집단을 나누고 연구자가 적극적으로 개입하는 Randomized Controlled Trial(RCT)이 강력할 수 밖에 없는 이유다. 이론적으로는 두 집단을 무작위로 나눈다면 confounder도 무작위로 나뉠 것이고 exposure of interest의 영향만 볼 수 있기 때문이다.  
  
그러나 RCT는 비싸고, 오래걸리고, 윤리적인 문제(예를들어 담배의 영향을 보고싶을 때 특정 집단에 강제로 담배를 피우게 할 수는 없다.)가 있다.  
  
Mendelian Randomization(MR)은 굉장히 재밌는 방법으로 이 문제를 해결한다.  
  
예를들어 Vit D level을 결정하는 유전자가 있다면? 혹은 그런 경향을 갖게하는(predispose) 유전자가 있다면?    
그런 유전자를 갖는 것은 순전히 random하다. 즉, 환경과 전혀 무관한 우연한 일이다.  
그럼 만약, low Vit D가 골절위험을 올린다면, 그 유전자를 가진 사람도 걸절위험이 높아야 한다.  
만약, low Vit D 와 높은골절위험의 association이 excercise같은 다른 교란변수들에 의한 것이라면 그 유전자와 골절위험은 무관할 것이다.  
  
굉장히 기발한 방법이다 !!!!
  
### Assessment of the genetic and clinical determinants of fracture risk: genome wide association and mendelian randomisation study
Mendelian Randomization을 아주 잘 적용한 논문이 있다.  



### 감상
1. RCT

2. 질병의 원인연구 
monogenic disorder(유전자 하나로 결정되는 질병)을 제외하면 대부분의 질병은 유전+환경+(그 둘의 상호작용)으로 아주 복잡하게 결정된다. 그러나 이것을 모두 고려하는 연구는 어려웠다. 그래서 
