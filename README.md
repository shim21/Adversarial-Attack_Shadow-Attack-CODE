# Adversarial-Attack_Shadow-Attack-CODE
■ Overview
1. Classifier output label뿐만 아닌 Certificate까지 타겟으로 하는 Adversarial Example 생성
2. Perturbation이 Shadow형태로 들어가 좀더 자연스러운 모습의 Adversarial Example을 생성
3. Shadow Attack의 특징
- Imperceptibility : 겉으로 보기에는 정상적으로 보이는 특징
- Misclassification : 타겟 클래스로 잘못 분류하도록 유도하는 특징(오분류)
- Strongly certified : 높은 보증 반경을 가지는 특징 

>>  Abstract
- Classifier의 labelling function과 Certificate generator를 둘 다 사용한 새로운 공격기법을 제시
- 이 방법은 adversarial examples의 비인지적 속성을 유지하면서도 class의 boundary와 멀리 떨어지게끔 위치시키는 perturbations를 적용
- Certifiably robust network가 이미지를 mislabel하도록 야기시키며 또 동시다발적으로 robustness의 “Spoofed” 한 certificate를 생성함

■ Certified Adversarial Robustness
- 입력 이미지가 주어졌을 때 특정한 크기의 𝑳_𝒑-boundary 안에서 adversarial example이 만들어 질 수 없도록 수학적으로 보장하는(guaranteeing) 방어 기법 유형
- Certificate robust를 가지고 있는 모델이 보았을 때, Certificate radius안에 Image가 있을 경우 정상적인 이미지로 인식 ->만약 perturbation이 섞인 Image가 있을 경우에도 그 Image가 radius 안에 있다면 정상적인 이미지라고 인식 

![image](https://user-images.githubusercontent.com/50358274/97447516-f9a15c80-1972-11eb-8033-980a4f7f5b07.png)

■ Randomized Smoothing
- 가장 각광을 받고 있는 Certified guaranteeing 방법 중 하나
- 모델을 학습시킬 때, 기존의 이미지에 특정 가우시안 분포에 따르는 변수 𝝈^𝟐 의 크기에 따라 무작위로 Perturbation을 뽑아내 그 Perturbation이 섞인 이미지를 사용하여 학습을 진행하는 방법

![image](https://user-images.githubusercontent.com/50358274/97447390-da0a3400-1972-11eb-8c73-b565dcb2ab8f.png)

■ Shadow Attack의 Loss function에 대한 설명은 아래와 같다.
![image](https://user-images.githubusercontent.com/50358274/97448438-ffe40880-1973-11eb-889a-294f87117d32.png)
![image](https://user-images.githubusercontent.com/50358274/97448473-0a060700-1974-11eb-9c3c-b12974db7156.png)
