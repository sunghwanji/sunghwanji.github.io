---
title : "[Mathematics & Statistics] Nested Cohort Study, Sensitive Analysis, E-value"
tags:
  - Mathematics & Statistics
use_math: false
---

[(이전글)
[Medicine] Association Between Incident Exposure to Benzodiazepines in Early Pregnancy and Risk of Spontaneous Abortion](https://sunghwanji.github.io/2019/09/29/Medicine-Association-Between-Incident-Exposure-to-Benzodiazepines-in-Early-Pregnancy-and-Risk-of-Spontaneous-Abortion.html)에서 리뷰한 논문의 몇가지 통계적 테크닉들에 대한 포스팅.  
<br>
### I. Nested Cohort Study
##### 1. Types of Epidemiological Studies
역학연구(Epidemiological Study)는 아래와 같이 나눌 수 있다.(Adapted from Monson (1990).)  
<br>
I. Experimental  
&nbsp;&nbsp;A. Clinical  
&nbsp;&nbsp;B. Population  
 
II. Observational  
&nbsp;&nbsp;A. Descriptive  
&nbsp;&nbsp;&nbsp;&nbsp;a. Disease surveillance and surveys  
&nbsp;&nbsp;&nbsp;&nbsp;b. Ecological  
&nbsp;&nbsp;B. Analytical  
&nbsp;&nbsp;&nbsp;&nbsp;a. Longitudinal  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ㄱ. Cohort (follow-up)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ㄴ. Case-control (case-comparison)  
&nbsp;&nbsp;&nbsp;&nbsp;b. Cross-sectional  
<br>
 연구자의 개입 유무에 따라 I.Experimental Study와 II.Observational Study를 나눌 수 있다.  
 연구 시작 전 명확한 가설의 유무에 따라 II-A. Descriptive Study와 II-B. Analytical Study를 나눌 수 있다.  
<br>
**Nested Cohort Study는 II-B.Observational Analytical Study의 variant 중 하나이다.**  
<br>
##### 2. Observational Analytical Study  
a. Case-control Study  
b. Cohort Study  
c. Nested Case-control Study  
d. Case-cohort Study
대표적인 Observational Analytical Study의 두가지 방법론은 a, b이며 c,d는 두 가지의 특징을 섞은 잡종이다.  
<br>
##### 3. Nested Case-control Study
이 연구에서 쓰인 Nested-cohort Study는,  
Cohort 안의 Case-control Study라고 볼 수 있다.  follow-up과정 중에 case가 생기면(즉, 질병이 발생하면) 그 시점에 age 등의 변수를 맞추어 control을 배정해 준다.(대략 1:4-5의 비율로)  
이 연구 디자인은 주로 exposure of interest가 측정하기 어렵거나(비싸거나), case가 드물 때 사용한다.  
<br>
##### 4. Advantages
1. control이 case와 같은 population에서 추출된다.  
2. **full cohort study보다 시간과 비용의 측면에서 효율적이다.**  
3. 노출에 대한 데이터를 대체로 진단 이전에 모으기 때문에 conventional case-control study에 비해 cause-effect interpretation에 적합하며, recall bias가 문제되지 않는다.    
<br>

주로, research question에 적절한 cohort를 갖고 있으며, 그 data의 subset을 구성하여 분석함으로서 효율적이며, statistical power를 잃지 않을 때 사용할 수 있다.  
<br>
##### 5. Example 
<img src="https://i.imgur.com/SFBdtD4.png" alt="Flow chart" style="display:block;margin:0 auto;">
<br>
내가 리뷰한 논문을 보면, Quebec Pregnancy Cohort에서 exclusion criteria에 해당하는 산모를 제외한 262,070명의 산모 중 7%의 Spontaneous abortion(자연유산) 군에서 제태연령 6주~19주에 일어난 27,149명의 산모가 Case였다. Spontaneous abortion이 일어나지 않은 233,530명의 산모 중 Case와 나이,제태연령으로 1:5로 matching 한 134,305명의 산모가 Control로 배정이 되었다.  
<br>
즉, 하나의 코호트 안에서 case-control study를 한 nested case-control study의 예시였다.  
<br>
##### 6. Why did they need this method ?
위에서 보았듯이, nested case-control study는 case이외의 집단 중 일부만을 control로 선정함으로서 크게 두가지 경우에 이득을 얻는다.  
  
1. cohort에서 case의 비율이 굉장히 작을 때  
2. exposrue of interest가 측정하기 어려울 때(비쌀 때)  
  
그럼 왜 이 연구자들은 이 연구방법을 썼을까?  
spontaneous abortion이 일어난 7%가 그렇게 적어보이지도 않으며, exposure of interest인 benzodiazepine 노출력은 청구데이터로 얻었기 때문에 모든 개개인에 대해 데이터가 있을 것 같다.  
  
궁금증을 해결하기 위해 학부 때 nested case-control study에 대해 강의해주셨던 한양의대 예방의학과 김미경 교수님께 메일을 드렸고 아래와 같은 대답을 얻었다.  
  
>>> 1. 7%의 발생을 rare하다고 말할 수 있는가?   
발생을 관찰 할 때 딱 잘라 몇 %를 기준으로 rare와 common을 구분하기는 어렵지만, 보통 10%를 기준으로 말하기는 한다.   
>>> 2. exposure of interest가 측정하기 어려운가?  
nested case-contorl study는 expensive한 biomarker를 측정해야할 때 많이 쓴다. 그런데 이 논문은 그런 연구는 아니다.  
>>> 3. 그럼 왜 썼을까?  
대상자의 관찰기간이 1998에서 2015로 상당히 긴 기간 cohort가 구축된 것이고 pregance loss가 일어난 시점과 전혀 다른 시점의 대상자들이 비교가 되면 교란변수로 측정되지 않은 너무 많은 인자들이 개입될 수 있다고 본 것 같고 loss가 일어난 월령 또한 주요한 confounder로 본 것 같다. 그래서 matching으로  gestational age 와 calendar year를 이용해서 이와 관련된 confounders를 미리 잡고 분석을 하겠다는 의도로 해석된다.  

### II. Sensitive Analysis

### III. E-Value


[참고자료]
1. https://en.wikipedia.org/wiki/Nested_case%E2%80%93control_study
2. Ernster, Virginia L. "Nested case-control studies." Preventive medicine 23.5 (1994): 587-590.
