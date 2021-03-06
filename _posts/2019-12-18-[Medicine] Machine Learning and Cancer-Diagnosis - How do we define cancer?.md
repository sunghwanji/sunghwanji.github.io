---
title : "[Medicine] Machine Learning and Cancer-Diagnosis - How do we define cancer?"
tags:
  - Data Science
  - Medicine
use_math: falses
---

### 평소 가지고 있던 궁금증
2016년 갑상선암의 특정타입이 암이었다가 양성으로 바뀐 바 있다.([링크](https://www.yna.co.kr/view/AKR20160415150400017)) 난소종양은 경계성(Borderline)이라는 진단명이 있다. 최근에 흉부외과를 돌면서 안 사실인데, 흉선종이 과거에는 양성과 약성으로 나뉘었지만 최근 모든 흉선종을 암이라고 보고 있다고 한다. 특정 '암'의 특정 병기의 5년 생존률이 100%에 수렴한다.  

**암은 어떻게 정의하는것일까?** 현미경적 소견으로 정의하는 것일까? 임상적으로 정의하는 것일까?  
이게 지금까지 내가 갖고 있던 궁금증이었다.  

이번 NEJM(The New England Journal of Medicine)에 실린 글을 읽었는데, 위의 궁금증에 해답을 주지는 못하지만 최근 이슈가 되고있는 머신러닝과 관련해서 고민해 볼만한 글인 것 같아서 포스팅 해보려 한다.  

### Machine Learning and the Cancer-Diagnosis Problem ? No Gold Standard
[논문링크(N Engl J Med 2019; 381:2285-2287 DOI: 10.1056/NEJMp1907407)](https://www.nejm.org/doi/full/10.1056/NEJMp1907407?query=TOC)

##### 1.  병리이미지에 ML이 쓰이는 원리  
  **지도학습(supervised learning)**. 즉,  인간이 "cancer", "not cancer"로 라벨링(external starndard) 한것을 보고 컴퓨터가 이미지에서 패턴(색, 모양, 모서리)을 학습하는 것이다.  
![사진](https://www.nejm.org/na101/home/literatum/publisher/mms/journals/content/nejm/2019/nejm_2019.381.issue-24/nejmp1907407/20191206/images/img_small/nejmp1907407_f1.jpeg)

##### 2. 현재의 암진단 : **the lack of a histopathological "gold standard"**  
  암(cancer)을 어떻게 정의할까? 두가지 관점이 있다.  
  
  임상가들은 동적(dynamic)인 정의에 관심이 있다. 임상가들에게 암은 증상(국소적 침투와 원격전이를 통해)을 일으키고 치료하지않을때 사망에 이르게 하는 것이다.  
  
  반면에, 병리의사들은 정적(static)인 정의에 관심이 있으며, 그들은 세포와 그 주변 구조의 모양과 다양한 바이오마커들으로 암을 정의한다.  
  
  특히, 암의 정의에 대한 문제는 병리의사들 사이의 관찰자간일치도(interobserver agreement)문제에서 두드러진다. 즉, 병리의사들 사이에서 어떤 게 임상적으로 의미있는 암인지에 대한 불일치가 있다는 것이다(이 문제는 전립선, 갑상선, 유방 병변과 악성흑색종에서 두드러진다). 근래에는 병리의사들에게 암을 조기에 진단하도록 요구하기 때문에, 아주 미묘한 현미경소견에 대해 판단해야 한다. 간혹 임상적인 정의에 맞지 않는 것을 암이라고 진단하기도 한다.  

##### 3. 이러한 현 상황에서 ML의 역할은?  
ML은 external standard, 즉  인간의 라벨링, 에 의존하기 때문에 위의 문제를 해결할 수 없다.  

ML은 확실히 인간보다 더 일관되고(consistent) 복제가능한(replicable) 진단을 할것이다. 그러나 그 진단이 '진짜'라는 보장은 없다. 즉 그 진단이 임상적으로 의미 있는 암을 진단하는데 인간보다 잘할 것이라는 보장이 없다는 것이다. 인간이 위의 문제를 풀지 못하면 ML도 풀지 못할 것이라는 거다. 오히려, ML이 진단의 정확도 개선을 하지 못하고, 효율만 증가시킨다면 **과다진단문제를 악화**시킬 것이라고 저자는 주장한다.  

##### 4. 저자가 제시한 방법  
어쨌든 ML이 재현성(reproducibility)의 면에서 장점이 있지만 임상가들은 과다진단을 피하고 싶다. 저자는 병리의사들간의 의견불일치정보를 이용하자고 주장한다. 즉, total agreement regarding the presence of cancer, total agreement regarding the absence of cancer, and disagreement regarding whether cancer is present 세가지 분류로 나누자는 것이다.  

그럼으로서 세가지의 장점이 있는데,  
효율적이다(efficient). 빠르게 위험도를 구분(triage)함으로서 병리의사들이 애매한 병리학적 소견에 집중할 수 있게 한다.  
솔직하다(honest). 즉 '애매하다'고 진단을 함으로서 임상가들과 환자들이 치료적 개입(intervention)에 보수적으로 할 수 있게한다.  
신중하다(judicious). 애매한 병변(intermediate lesions)에 대해 더 알아보고 연구할 수 있게 한다.  

모두에게 가장 중요한 것은 **"그 암 진단이 환자의 삶의 길이와 질에 영향을 주느냐."** 이다.  
저자는 이러한 방법으로 회색지대(gray area)를강조함으로서 ML의 장점을 살리면서 단점을 개선하자고 주장한다. 그럼으로서 **진짜 '암'** 이란 무엇인지에 대한 해답을 얻어낼 수 있을 것이라고 말하고 있다.

### 풀리지 않는 궁금증
이 글을 읽고 나니, 현미경적으로 어떻게 보이든, 결국엔 **"임상적인 의미가 있는 암"**을 진단하는 것이 중요하다는 생각이 든다. 어쨌든 그걸 진단하기 위한 현재의 가장 중요한 진단방법은 떼서 현미경으로 보는 것이다.  

그럼 지금 우리가 암이라고 진단하고 있는 현미경적 소견은 어떻게 증명된것일까? '이런 모양인 경우는 통계를 내보니 임상적으로 암이더라..'이런식으로 증명한것인가....(내가 병리실습을 안돌아서..ㅎㅎ)  

나중에 수련받을 때 여쭤봐야겠다...
  
  
  
### My Question : How do we define cancer ?
In 2016, a specific type of thyroid cancer became recognized as a benign tumor. Some ovarian tumors are diagnosed as borderline, not malignant neither benign. I recently learned during the rotation in the thoracic surgery department that we see all of the thymoma, some of which were recognized as as a benign tumor, malignant. The 5-year survival rate of a certain cancer is almost 100%.  

**How do we define cancer?** Do we define them by microscopic findings? Or, Do we define them clinically?  

This was the question I've had so far.  

Recently, I've read an article from NEJM(The New England Journal of Medicine). I'm going to post about it since i think it is worth to consider.  

### Machine Learning and the Cancer-Diagnosis Problem ? No Gold Standard
[Article(N Engl J Med 2019; 381:2285-2287 DOI: 10.1056/NEJMp1907407)](https://www.nejm.org/doi/full/10.1056/NEJMp1907407?query=TOC)
##### 1. Principles of Using Machine Learning to Pathology
Most machine learning algorithms used in pathology are trained by means of a process called **supervised learning**. In other words, the computer is presented with images and learns patterns(color, character, margin) from external standards(cancer vs not cancer) which have been labeled by humans.  

##### 2. Cancer Diagnosis of Today : the Lack of a Histopathological "Gold Standard"
What constitutes cancer? There are 2 points of view.  

Clinicians are interested in dynnamic definition. For clinicians, cancer is a tumor which causes symptoms through local infiltration and distant metastasis and leads to death if left untreated.  

On the other hand, pathologists are interested in static definition. They define cancers by the appearance of cells, surrounding tissue architecture, and various biomarkers.  

In particular, the issue of cancer definition is highlighted in the interobserver disagreement issue among pathologists. That is, there is a mismatch among pathologists about which is clinically meaningful cancer.(Especially in prostate, thyroid, breast lesion and malignant melanoma) Recently, since pathologists are required to diagnosis early cancer, they should judge on subtle microscopic findings. Sometimes, that cancer doesn't fit the clinical definition.  

##### 3. Then, What Machine Learning Can Do ?
Machine learning(ML) cannot solve the problem above since it relies on external standards, labeled by humans.  

Diagnoses of ML will undoubtedly be more consistent and more replicable than those based on human interpretation. However, it won't necessarily be closer to the truth. In other words, ML may not be any better than humans at determining which tumors are destined to cause symptoms or death. Rather, the author argues that if ML fails to improve the accuracy of diagnosis but increases the efficiency, it will exacerbate the problem of **over-diagnosis**.  

##### 4. The Author's Suggestion

Clinicians want to avoid overdiagnosis, though ML has the merit of reproducibility. The author suggests to use the information of disagreement. In other words, using 3 categories;  total agreement regarding the presence of cancer, total agreement regarding the absence of cancer, and disagreement regarding whether cancer is present  

The advantages to using these are:  

It would be efficient. It helps pathologists to focus on equivocal findings by immediately triaging slides.  

It would be honest. It enables clinicians and patients to consider more conservative treatment options by telling them the lesions are ambiguous.  

It would be judicious. We can study and explore further for intermediate lesions.  

The most important question to everyone is **"Does the cancer affects the quality and length of the patient's life?"**  
The author argues that by highlighting these gray areas, we can emphasize the strength and ameliorate the weakness of ML. Finally, we can get closer to the answer about what constitutes the **'true' cancer**.  

### Unsolved Questions
After reading this article, I realized that what is important for us is to diagnose **"clinically meaningful cancer"**, no matter how it looks microscopically. Anyhow, the current best diagnostic method for clinically defined cancer is to look at it microscopically.   

If this is the case, how did the microscopic findings that we recognized as markers for cancer have been proven? Do we prove them through statistical analysis, finding the correlation of the findings and clinical outcomes?  

These are the questions I have to solve during my residency.  
