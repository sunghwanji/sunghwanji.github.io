---
title : "[Digital Healthcare] AI Medicine & Digital Hospital Joint Symposium"
tags:
  - Digital Healthcare
use_math: falses
---

2020.01.14 연세대학교 신촌세브란스 병원에서, 용인세브란스 병원 개원 기념으로 심포지엄을 열었다. AI Medicine & Digital Hospital Joint Symposium이라는 이름으로 Cleveland Clinic과의 Joint Symposium이었다. 사실상, 두 기관에서 진행되는 Data Science 연구들을 소개하는 자리인듯 했다.

# Session I. Clinical application of AI and Digital Technology
### Translational Machine Learning and AI Approaches for Precesion Oncology - From Tissue to Single Cell and More (Tae Hyun Hwang, Cleveland Clinic)
  
  
##### 1. 어떤 환자에게 면역항암제를 써야할까?  

Tumer mutation burden(TMB), Microsatellite instability high tumor(MSI-H), PD-L1 발현 등은 neo-antigen 발현에 의한 면역반응으로 종양세포가 제거될 확률도 높아지기 때문에 암에 대한 면역반응을 올리는 Immunotherapy반응성과 연관이 되어있음이 알려져 있다.  
**sequencing을 해야만 알 수 있는 TMB, MSI-H 정보를 histopathology image로 알 수 있다면?**  
  
TMB가 높거나 MSI-H 임에도 Immunotherapy에 반응하지 않는 환자가 있다.  
그런 환자들은 tumor에 infiltrating 하는 lymphocyte가 적은 것이 아닐까?  
**cancer tissue에서 TMB, MSI-H와 tumor infiltrating lymphocyte(TIL)의 mapping을 보면 immunotherpay 반응성을 더 정확히 예측할 수 있지 않을까?**  

결과 : 잘되더라. 근데, The Cancer Genome Atlas(TCGA)로 학습한 알고리즘으로 yonsei data로 테스트 해봤더니 잘 안되더라.. ethnicity도 중요한듯 
       
  
(reference : Deep learning can predict microsatellite instability directly from histology in gastrointestinal cancer. Natrue Medicine)  

##### 2. 어떤 환자에게 CAR-T therapy를 해야할까?  
기적의 항암제(급성림프구성백혈병 환자 63명을 대상으로 한 2상 임상시험에서 3개월만에 완치율 83%)라고 불리는 CAR-T therapy에 대한 반응성 예측  
  
**CAR-T therapy란?**
- 암환자의 T-Cell 추출  
- 바이러스 벡터를 이용하여 암세포 특이적 키메릭 수용체 (CAR)를 발현  
- 세포 배양  
- 환자에게 재주입하여 암세포 공격  

>>>> Take Home message  
1. Carefully designed machine learning algorithms could identify mechanisms of response and resistance to immunotherapy treatment.  
2. Histopathology images could be used to predict clinical phenotypes related with immunotherpay response.  
3. Image is only providing a snapshot of phenotypes driven by genomic/epigenetic/transcriptomic/etc. changes. Be cautious and aware of limitations of the use of the image.  
4. Think about your goal again and again. Single Cell is powerful but would not be your solution.  
5. seeing is believing ? No. Manually check your gene expressions if it is too good to be true.

**느낀점 : 최근 연구자들이 multi-omics(genome, proteome, transcriptome....) data에 관심이 많은 듯 한데, 알려진것도 많지 않고, 돈도 많이들고, 어렵다. histopathology image는 multi-omics의 결과물(phenotype)일텐데, image를 deep learning으로 효과적으로 분석해서 multi-omics의 정보를 어느정도 대변할 수 있다면?**

### Clinical Impact of AI in Breast Imaging (Eun-Kyung Kim, YUCM)
Lunit Insight MMG 개발에 직접 관여하신 분인듯.  
breast cancer screening에 쓰이는 mammography 판독을 딥러닝모델이 잘하더라..  
간혹 있는 false negative들은 충분한 데이터를 학습시키면 개선될 것이라고 생각하심.
  
앞으로 해야할 것들
- Integration with PACS  
- Workflow improvement  
  지금은 판독을 찍은순서대로 하고 있는데, deep learning model이 triage를 해주면 workflow가 효율화 될것이다.
- Real-world application  
  실제 screening seetting에서 clinical impact를 증명해야한다.  
  
>>>> Summary  
1. The AI-CAD : ready for clnical use  
2. Studies within a screening scenaro should be performed to validate previous findings and to evaluate the real effect of AI support in screening.  
3. We as clinicians should pay more attention to whether research on this tool is going in the right direction.  
  
### Application of machine learning to ICU patients for early detection of clinical problems and prediction of outcoms 
**Heterogeneity of Delirium** 
- Motor Subtype : hyperactive, hypoactive, mixed  
- Etiology : infections, neurological injury or disease, medications, alcohol withdrawal, electrolyte imbalance, organ failure, hypoxia, surgery..  
- Setting : surgical, medical, ICU, palliative care..  
- The presence or absence of prior demetina  
-> Validity of a diagnsosis?  
-> Inconsistent results  
-> Low generalizability and Low translation into clinical practice  
(Harwood and Teale, Int J Geriatr Psychiatry, 2018)  
즉, 위와같은 특성때문에 현재 delirium을 제대로 진단하고 management 하기 힘들다.  

**Delirium을 detection 혹은 prediction할 수 있는 biomarker가 있을까?**  

delirium환자에서 heart rate variabilty가 증가되어 있다는 선행연구를 바탕으로 연구디자인을 함.  
  
Heart rate variability(HRV)와 Machine Learning으로 Delirium 과 Non-Delirium을 구분할 수 있을까?  

매일 아침 정신과의사가 delirium을 evaluation하고, 간호사가 하루 세번 평가를 하고 그 데이터로 학습을 시킴.  
  
결과 : 연구자의 HRV with machine learning으로 만든 알고리즘이  massive amounts of clinical information으로 예측하는것과 비슷했다.  
  
**즉, 매일 아침 정신과 의사가 delirium인지 평가 하지 않아도 HRV라는 biomarker로 delirium을 detection 할 수 있겠다..**  

+) 연자는 정신과 의사였지만, machine learning으로 ICU mortality를 예측하는 연구에 대해서도 설명해 주셨다. delirium 예측보다 더 잘되는듯.  

**느낀점 : 우리가 배우는 질병에는 임상적으로(환자의 병력과 신체진찰만으로) 진단하는 질병이 꽤 많다. 그러한 진단들은 부정확할 수 있는데, 새로운 방법론들로 진단을 더 정확하게 하는 biomarker를 만들 수 있지 않을까???**  
  
# Session II. AI in Cardiovascular Imaging  
### Artificial Intelligence in Cardiac Magnetic Resonance Imaging - The Promise of Revolutionary Translational Clinical Applications (Deborah kwon, Cleveland Clinic)  
**Conclusion**  
AI holds much promise to revolutionize the role of clinical Cardiac MR  
- Imporve efficiency, reproducibility, accuracy of reporting  
- Improve diagnostic accuracy - Radiomics  
- Identify novel patterns of disease to improve risk stratification  
- Potential for developing precision/personalized medicine  
- Can be used to guide therpay  
- May be useful for deriving cost-effective therapies  
  
질의응답 : 
  
### Applications of Artificial Intelligence in Cardiovascular Computed Tomography (Young Joo Suh, YUCM)  
**What is radiomics ?**    
- Definition  
  - Conversion of digital medical images into mineable high-dimensional data  
  - To extract large number of quantitative features from medical imagese using data-characterization algorithms  
- Theoretical Background  
  - Biomedical images contain information that reflects underlying pathophysiology  
  - Potential to uncover disease characteristics that fail to be appreciated by the naked eye  

**Summary**  
- Expanding role of cardiac CT  
  - Image reconstruction : denoising  
  - Segmentation and quantification : coronary calcium, heart chamber  
  - Interpretation : ML-based FFR  
  - Prognosis


### Technical Aspects of AI-based Cardiac Image Analysis with Deep Learning (Hwiyoung Kim, YUCM)  

# Session III. Precision Medicine for Neurogenetic Diseases  
### Epilepsy Genetics & Variant Interpretation Informatics (Dennis Lal, Cleveland Clinic)  
### Epilepsy Management in thee Era of Precision Medicine (Hoon-Chul Kang, YUCM)  
### Brain Somatic Mutations in FCD and Other Epilesy Associated Lesions (Jeong-Ho Lee, KAIST)








