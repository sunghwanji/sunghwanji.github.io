---
title : "[Digital Healthcare] Automated EKG Interpretation"
tags:
  - Digital Healthcare
use_math: false
---

### Background
1) 응급실에서 근무중에, 30대 남자환자가 축구하다가 심정지가 와서 오고 있다고 119에서 전화가 왔다. 환자가 도착했을 당시에는 ROSC(return of spontaneous circulation)된 상태였다.  
상황을 들어보니 축구를 하다가 심정지가 왔고 친구들이 심정지임을 판단하고 흉부압박을 하면서 AED(Automated External Defibrillator)를 적용했고, 기계가 자동으로 심실세동을 감지해 defibrillation(세동제거)까지 성공적으로 시행했다.(우리나라 일반인들의 응급상황 대처능력에 놀랐다.)  
  
2) 병동에서 EKG를 찍다보면, 바로 자동판독이 옆에 찍혀나오는데, 꽤 정확하다. 근데, 루틴에서 좀 벗어나거나 노이즈가 섞이면 그닥 믿을만한 결과는 아닌것 같다. 간혹 내가 봐도 쉬운 EKG를 틀리기도 한다.
  
  
현재 논의중인 '의료인공지능'도 결국 의사의 의사결정을 대체하지는 않고 효율화하는 방향 즉, CDSS(Clincical Decision Supporting System)으로 발전할 것이라는데 대부분이 동의하시는 것 같다.  
  
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
 1. Signal Processing : 시그널을 얻어내고, 아날로그를 디지털로 바꾸고, 노이즈를 없애기.  
 2. Wave Recognition : P-wave, QRS-complex, T-wave의 시작과 끝을 정한다.  
 3. Measurements of intervals (PR, QRS, QT) and amplitude parameters : 이 지점에서 제조사간에 차이도 있고, arrythmia가 있을 때 기술적 문제들이 있는 듯 하다.  
 
 각 wave의 정의, 측정법, 판독문의 표준화가 아직 되어있지 않다. 이것은 임상적인 결과에 차이를 미칠 수 있다.  
 예) 심부전의 치료법 중 하나인, Cardiac resychronization therpay의 경우 QRS 길이가 적응증에 매우 중요해서, QRS 길이 측정법에 예민하다.  
 
##### Algorithm Accuracy
EKG 자동판독 알고리즘의 정확도를 연구하는데 문제점은  
대부분의 연구들이 알고리즘과 전문가의 판독을 비교하는데,  
알고리즘 별로 제조사들이 다르고, 전문가의 EKG 판독 자체가 주관적인 요소가 있어서 관찰자간의 차이가 꽤 크다.  
또한, 알고리즘을 테스트하는 데이터셋이 전체 모집단을 대표하지 못해서, 실제의료현장을 대변하지 못한다.  
제조사들이 알고리즘을 공개하는것을 꺼려해서, 제조사간 정확도 비교가 안되고 있다.(저자는 제조사간의 협업을 강조하고 있다.)  
  
(알고리즘 정확도에 대한 연구들이 논문에 잘 리뷰되어 있으니, 궁금하신 분들은 읽어보시는 것도 ㅎㅎ)  

##### Practical Aspects


  