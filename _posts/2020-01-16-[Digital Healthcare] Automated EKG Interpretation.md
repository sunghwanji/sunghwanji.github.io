---
title : "[Digital Healthcare] Automated EKG Interpretation"
tags:
  - Digital Healthcare
use_math: false
background: '/img/posts/EKG.jpg'
---

### Background
1) 응급실에서 근무중에, 30대 남자환자가 축구하다가 심정지가 와서 오고 있다고 119에서 전화가 왔다. 환자가 도착했을 당시에는 ROSC(return of spontaneous circulation)된 상태였다.  
상황을 들어보니 축구를 하다가 심정지가 왔고 친구들이 심정지임을 판단하고 흉부압박을 하면서 AED(Automated External Defibrillator)를 적용했고, 기계가 자동으로 심실세동을 감지해 defibrillation(세동제거)까지 성공적으로 시행했다.(우리나라 일반인들의 응급상황 대처능력에 놀랐다.)  
  
2) 병동에서 EKG를 찍다보면, 바로 자동판독이 옆에 찍혀나오는데, 꽤 정확하다. 근데, 루틴에서 좀 벗어나거나 노이즈가 섞이면 그닥 믿을만한 결과는 아닌것 같다. 간혹 내가 봐도 쉬운 EKG를 틀리기도 한다.  
전문가선생님들은 자동판독문을 어떻게 이용하는 지 모르겠지만, 인턴의사인 나와 내동료들, 그리고 아마도 수련 초반의 의사들 상당수가 screening 용도로 판독문을 먼저 볼 것이다.
  
  

현재 논의중인 '의료인공지능'도 결국 의사의 의사결정을 대체하지는 않고 효율화하고 돕는 방향 즉, CDSS(Clincical Decision Supporting System)으로 발전할 것이라는데 대부분이 동의하시는 것 같다.  
  
그렇다면 2)는 현재 이슈가되는 '의료인공지능'과는 임상적으로는 크게 다르지 않아보인다.  

심지어 1)은 특정 조건에서 의사의 컨펌없이 치료적 개입까지 한다.  
  
  
### Computer-Interpreted Electrocardiograms: Benefits and Limitations
Automated EKG Interpretation과 현재 논의 중인 '의료인공지능'과 비교하려고 해보니 궁금한 것이 너무 많아진다.  
일단, Automated EKG interpretation에 대해 먼저 공부해 봐야겠다. 생각보다 볼 자료가 없었는데, 잘 정리되어 있는 논문이 하나 있어서 읽어보았다.    
[Jürg Schläpfer, Hein J. Wellens,
Computer-Interpreted Electrocardiograms: Benefits and Limitations,
Journal of the American College of Cardiology,
Volume 70, Issue 9,
2017](https://www.sciencedirect.com/science/article/pii/S0735109717387946#bib22)
##### Automated EKG Interpretation
 - 매해 전세계적으로 수백만장의 EKG가 찍히고있으며, 대부분 자동판독이 되고 있다.  
 - 1950년대부터 EKG 판독을 자동화하려는 노력이 있었으며 그이후로도 프로그램간에 표준화를 하고, 정확도를 높이려는 노력을 계속 해왔다.  
 - 그럼에도 아직도 국제표준은 없는 상태이다.  
 ![그림](https://ars.els-cdn.com/content/image/1-s2.0-S0735109717387946-gr5.jpg)
 
##### General Comments About Technical Aspects
대략 이런 순서대로 진행되는듯 했다.
 1. Signal Processing : 시그널을 얻어내고, 아날로그를 디지털로 바꾸고, 노이즈를 없애기.  
 2. Wave Recognition : P-wave, QRS-complex, T-wave의 시작과 끝을 정한다.  
 3. Measurements of intervals (PR, QRS, QT) and amplitude parameters : 이 지점에서 제조사간에 차이도 있고, arrythmia가 있을 때 기술적 문제들이 있는 듯 하다.  
 
 즉, rule-base로 접근하는 것으로 이해된다.  
   
 문제는, 각 wave의 정의, 측정법, 판독문의 표준화가 아직 되어있지 않다. 이것은 임상적인 결과에 차이를 미칠 수 있다.  
 예) 심부전의 치료법 중 하나인, Cardiac resychronization therpay의 경우 QRS 길이가 적응증에 매우 중요해서, QRS 길이 측정법에 예민하다.  
 
##### Algorithm Accuracy
EKG 자동판독 알고리즘의 정확도를 연구하는데 문제점은  
대부분의 연구들이 알고리즘과 전문가의 판독을 비교하는데,  
알고리즘 별로 제조사들이 다르고, 전문가의 EKG 판독 자체가 주관적인 요소가 있어서 관찰자간의 차이가 꽤 크다.  
또한, 알고리즘을 테스트하는 데이터셋이 전체 모집단을 대표하지 못해서, 실제 의료현장을 대변하지 못한다.  
제조사들이 알고리즘을 공개하는것을 꺼려해서, 제조사간 정확도 비교가 안되고 있다.(저자는 제조사간의 협업을 강조하고 있다.)  
  
(알고리즘 정확도에 대한 연구들이 논문에 잘 리뷰되어 있으니, 궁금하신 분들은 읽어보시는 것도 ㅎㅎ)  

##### Practical Aspects
Automated EKG Interpretation은 인간전문가를 대체하는 것이 아니라 돕는 것이다.

EKG의 촬영 퀄리티만 좋다면, computerized interpretation은 전문가에게 대략 24~28%의 시간을 절약해 준다고 한다.  

computerized interpretation은 medical error을 줄여주고 임상가의 시간을 절약해주고, 의료비용을 절약하게 해준다.   

자동판독은 정확할때는 의사의 진단에 도움이 되지만 부정확하면 나쁜 결과를 유도한다. 이러한 결과는 매해 전세계에 10,000건의 부작용이나 피할수 있던 사망의 원인이 된다고 한다. 가끔은 필요없거나, 부적절하거나 심지어는 위험한 care를 야기하기도 하다.  

논문에 따르면, 내과 레지던트 조차도 자신의 EKG 판독에 자신이 없을 때도 있고, 틀릴때도 많다. 미국의 심장내과 펠로우들은 3년간의 수련기간동안 3000~3500장의 EKG를 판독한다고 한다.  

저자는 계속해서, EKG 자동판독의 정확성개선, 표준화를 강조한다.  


  
### 궁금증들...
2017년 8월의 논문을 감안하더라도, 생각보다 지적하는 문제들이 많다. 의사의 부정확한 EKG 판독은 환자의 치료결과에 직접적으로 영향을 미칠 수도 있다. 그럼에도 어떤 임상상황이든 EKG 촬영과 동시에 자동판독이 찍혀나온다. 심지어 의사컨펌없이 자동으로 치료적 개입을 하기도 한다. 그러나, 아직 경험이 적지만, 지금까지 임상에서 문제가 되었다는 얘기를 들은 적은 없다.  
  
내 짧은 식견으로는, EKG 자동판독과 현재의 루닛, 뷰노 등에서 하는 '의료인공지능'과 임상적으로는 크게 다르지 않아보인다. EKG 자동판독이 도입될 때는 어떤 분위기였을까? clinical benefit의 증명을 요구하고, 특정상황에서 RCT를 요구하고, 판독이 틀렸을 때의 책임소재에 대해 논의하는 등등의 현재 많은 이슈들이 그때도 문제가 되었을까?  
  
현재의 논의들이 의미가 없다기 보다는, 현재 논의되는 딥러닝 혹은 머신러닝 모델들이 **'인공지능'이라고 이름이 붙었다고 특별히 다를게 있나?** 라는 의문에 대해 해결을 하고 싶다는 것이다.  

### EKG 자동판독 vs 딥러닝 기반의 영상판독
그냥 재미로 ㅎㅎ EKG 자동판독과 현재 딥러닝 기반의 영상판독의 차이점을 고민해 봤다.  
  
1) 전자는 공부해보니 생각보다 이론적 배경은 간단해 보였다. 기본적으로 **rule-base**라 black box 문제는 없어보였다. 반면에 후자는 (내가 딥러닝을 잘 모르지만) 기술적으로 '왜 잘되지?'에 대한 논의가 아직도 진행중이라고 들었다. 즉, 같은 모델이라도 **이론적 배경에 따라 다른 잣대**를 적용해야 될 수도 있겠다.
2) 전자는 인턴인 내 입장에서는 쏠쏠히 도움이 되지만 전문가들은 생각보다 잘 안볼 수도 있는 것 같다. 아직 도입이 안되서 잘 모르겠지만 후자는 전자와 비교가 안될정도로 clinical impact가 있을 수도?
  
그래도 나는 후자에 '인공지능'이라는 이름이 붙는 것의 의미가 매우 크다고 생각한다. 그 단어의 영향이 비전문가, 일반인, 언론에 미치는 영향이 매우 큰 것 같다.
