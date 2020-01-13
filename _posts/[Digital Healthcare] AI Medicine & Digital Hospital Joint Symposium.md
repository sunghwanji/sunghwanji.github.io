---
title : "[Digital Healthcare] Machine Learning and Cancer-Diagnosis - How do we define cancer?"
tags:
  - Digital Healthcare
use_math: falses
---


### Session I. Clinical application of AI and Digital Technology
##### Translational Machine Learning and AI Approachese for Precesion Oncology - From Tissue to Single Cell and More (Tae Hyun Hwang, Cleveland Clinic)
1. 어떤 환자에게 면역항암제를 써야할까?  
- Tumer mutation burden(TMB), Microsatellite instability high tumor(MSI-H), PD-L1 발현 등은 neo-antigen 발현에 의한 면역반응으로 종양세포가 제거될 확률도 높아지기 때문에 암에 대한 면역반응을 올리는 Immunotherapy반응성과 연관이 되어있음이 알려져 있다.
- sequencing을 해야만 알 수 있는 TMB, MSI-H 정보를 histopathology image로 알 수 있다면?  
  
- TMB가 높거나 MSI-H 임에도 Immunotherapy에 반응하지 않는 환자가 있다.  
- 그런 환자들은 tumor에 infiltrating 하는 lymphocyte가 적은 것이 아닐까?  
- cancer tissue에서 TMB, MSI-H와 tumor infiltrating lymphocyte(TIL)의 mapping을 보면 immunotherpay 반응성을 더 정확히 예측할 수 있지 않을까?  

결과 : 잘되더라... unpublished data도 아직 많은듯  
       The Cancer Genome Atlas(TCGA)로 학습한 알고리즘으로 yonsei data로 테스트 해봤더니 잘 안되더라.. ethnicity도 중요한듯 
       
  
reference : Deep learning can predict microsatellite instability directly from histology in gastrointestinal cancer. Natrue Medicine  

2. 어떤 환자에게 CAR-T therapy를 해야할까?  
기적의 항암제(급성림프구성백혈병 환자 63명을 대상으로 한 2상 임상시험에서 3개월만에 완치율 83%)라고 불리는 CAR-T therapy에 대한 반응성 예측  
CAR-T therapy  
- 암환자의 T-Cell 추출  
- 바이러스 벡터를 이용하여 암세포 특이적 키메릭 수용체 (CAR)를 발현  
- 세포 배양  
- 환자에게 재주입하여 암세포 공격  

Take Home message  
1. Carefully designed machine learning algorithms could identify mechanisms of response and resistance to immunotherapy treatment.  
2. Histopathology images could be used to predict clinical phenotypes related with immunotherpay response.  
3. Image is only providing a snapshot of phenotypes driven by genomic/epigenetic/transcriptomic/etc. changes. Be cautious and aware of limitations of the use of the image.  
4. Think about your goal again and again. Single Cell is powerful but would not be your solution.  
5. seeing is believing ? No. Manually check your gene expressions if it is too good to be true.

느낀점 : 최근 연구자들이 multi-omics(genome, proteome, transcriptome....) data에 관심이 많은 듯 한데,, 만약 그 결과인 phenotype정보가 histopathology image에 담겨있다면? 그것을 deep learning으로 효과적으로 분석할 수 있다면?



- 