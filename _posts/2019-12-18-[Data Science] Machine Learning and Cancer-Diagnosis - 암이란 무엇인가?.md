---
title : "[Medicine] Machine Learning and Cancer-diagnosis - 암이란 무엇인가?"
tags:
  - Data Science
  - Medicine
use_math: falses
---

#### 평소 가지고 있던 궁금증
2016년 갑상선암의 특정타입이 암이었다가 양성으로 바뀐 바 있다.([링크](https://www.yna.co.kr/view/AKR20160415150400017)) 난소종양은 경계성(Borderline)이라는 진단명이 있다. 최근에 흉부외과를 돌면서 안 사실인데, 흉선종이 과거에는 양성과 약성으로 나뉘었지만 최근 모든 흉선종을 암이라고 보고 있다고 한다. 특정 '암'의 특정 병기의 5년 생존률이 100%에 수렴한다.  
즉, 어쨌든 우리가 암이라고부르는게 절대적인것이 아니다.  

**암은 어떻게 정의하는것일까?** 현미경적 소견으로 정의하는 것일까? 임상적으로 정의하는 것일까?  
이게 지금까지 내가 갖고 있던 궁금증이었다.  

우연히 NEJM(The New England Journal of Medicine)에 실린 글을 읽었는데, 위의 궁금증에 해답을 주지는 못하지만 최근 이슈가 되고있는 머신러닝과 관련해서 고민해 볼만한 글인 것 같아서 포스팅 해보려 한다.  

#### Machine Learning and the Cancer-Diagnosis Problem ? No Gold Standard
[논문링크](https://www.nejm.org/doi/full/10.1056/NEJMp1907407?query=TOC)

1.  병리이미지에 ML이 쓰이는 원리  
  **지도학습(supervised learning)**. 즉,  인간이 "cancer", "not cancer"로 라벨링(external starndard) 한것을 보고 컴퓨터가 이미지에서 패턴(색, 모양, 모서리)을 학습하는 것이다.  
![사진](https://www.nejm.org/na101/home/literatum/publisher/mms/journals/content/nejm/2019/nejm_2019.381.issue-24/nejmp1907407/20191206/images/img_small/nejmp1907407_f1.jpeg)

2. 현재의 암진단 : **the lack of a histopathological "gold standard"**  
  암(cancer)을 어떻게 정의할까? 두가지 관점이 있다.  
  임상가들은 동적(dynamic)인 정의에 관심이 있다. 임상가들에게 암은 증상(국소적 침투와 원격전이를 통해)을 일으키고 치료하지않을때 사망에 이르게 하는 것이다.  
  반면에, 병리의사들은 정적(static)인 정의에 관심이 있으며, 그들은 세포와 그 주변 구조의 모양과 다양한 바이오마커들으로 암을 정의한다.  
  특히 암의 정의에 대한 문제는 병리의사들 사이의 관찰자간일치도(interobserver agreement)문제에서 두드러진다. 즉, 병리의사들 사이에서 어떤 게 임상적으로 의미있는 암인지에 대한 불일치가 있다는 것이다(특히 이문제는 전립선, 갑상선, 유방 병변과 악성흑색종에서 두드러진다). 근래에는 병리의사들에게 암을 조기에 진단하도록 요구하기 때문에, 아주 미묘한 현미경소견에 대해 판단해야 한다. 간혹 임상적인 정의에 맞지 않는 것을 암이라고 진단하기도 한다.  

3. 이러한 현 상황에서 ML의 역할은?  
ML은 external standard, 즉  인간의 라벨링, 에 의존하기 때문에 위의 문제를 해결할 수 없다.  
ML은 확실히 인간보다 더 일관되고(consistent) 복제가능한(replicable) 진단을 할것이다. 그러나 그 진단이 '진짜'라는 보장은 없다. 즉 그 진단이 임상적으로 의미 있는 암을 진단하는데 인간보다 잘할 것이라는 보장이 없다는 것이다. 인간이 위의 문제를 풀지 못하면 ML도 풀지 못할 것이라는 거다.오히려, ML이 진단의 정확도 개선을 하지 못하고, 효율만 증가시킨다면 **과다진단문제를 악화**시킬 것이라고 저자는 주장한다.  

4. 저자가 제시한 방법  
어쨌든 ML이 재현성(reproducibility)의 면에서 장점이 있지만 임상가들은 과다진단을 피하고 싶다. 저자는 병리의사들간의 의견불일치정보를 이용하자고 주장한다. 즉, total agreement regarding the presence of cancer, total agreement regarding the absence of cancer, and disagreement regarding whether cancer is present 세가지 분류로 나누자는 것이다.  
그럼으로서 세가지의 장점이 있는데,  
효율적이다(efficient). 빠르게 위험도를 구분(triage)함으로서 병리의사들이 애매한 병리학적 소견에 집중할 수 있게 한다.  
솔직하다(honest). 즉 '애매하다'고 진단을 함으로서 임상가들과 환자들이 치료적 개입(intervention)에 보수적으로 할 수 있게한다.  
신중하다(judicious). 애매한 병변(intermediate lesions)에 대해 더 알아보고 연구할 수 있게 한다.  
모두에게 가장 중요한 것은 **"그 암 진단이 환자의 삶의 길이와 질에 영향을 주느냐."** 이다.  
저자는 이러한 방법으로 grey zone을 강조함으로서 ML의 장점을 살리면서 단점을 개선하자고 주장한다. 그럼으로서 **진짜 '암'** 이란 무엇인지에 대한 해답을 얻어낼 수 있을 것이라고 말하고 있다.
