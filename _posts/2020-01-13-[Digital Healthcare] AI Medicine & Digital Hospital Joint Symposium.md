---
title : "[Digital Healthcare] AI Medicine & Digital Hospital Joint Symposium"
tags:
  - Digital Healthcare
use_math: falses
---


## Session I. Clinical application of AI and Digital Technology
#### Translational Machine Learning and AI Approachese for Precesion Oncology - From Tissue to Single Cell and More (Tae Hyun Hwang, Cleveland Clinic)
  
###### 1. 어떤 환자에게 면역항암제를 써야할까?  

Tumer mutation burden(TMB), Microsatellite instability high tumor(MSI-H), PD-L1 발현 등은 neo-antigen 발현에 의한 면역반응으로 종양세포가 제거될 확률도 높아지기 때문에 암에 대한 면역반응을 올리는 Immunotherapy반응성과 연관이 되어있음이 알려져 있다.  
**sequencing을 해야만 알 수 있는 TMB, MSI-H 정보를 histopathology image로 알 수 있다면?**  
  
TMB가 높거나 MSI-H 임에도 Immunotherapy에 반응하지 않는 환자가 있다.  
그런 환자들은 tumor에 infiltrating 하는 lymphocyte가 적은 것이 아닐까?  
**cancer tissue에서 TMB, MSI-H와 tumor infiltrating lymphocyte(TIL)의 mapping을 보면 immunotherpay 반응성을 더 정확히 예측할 수 있지 않을까?**  

결과 : 잘되더라. 근데, The Cancer Genome Atlas(TCGA)로 학습한 알고리즘으로 yonsei data로 테스트 해봤더니 잘 안되더라.. ethnicity도 중요한듯 
       
  
(reference : Deep learning can predict microsatellite instability directly from histology in gastrointestinal cancer. Natrue Medicine)  

###### 2. 어떤 환자에게 CAR-T therapy를 해야할까?  
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

#### Clinical Impact of AI in Breast Imaging (Eun-Kyung Kim, YUCM)
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
