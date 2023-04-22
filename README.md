# entropic_MIA_defense

This repo is study of the significance of entropy of the classification vector of a classification model, in relationship to membership inference attack (MIA), as specified in this paper: He, Xinlei, et al. "Membership-Doctor: Comprehensive Assessment of Membership Inference Against Machine Learning Models." arXiv preprint arXiv:2208.10445 (2022).

More specifically, this repo tries to compare several variations of defenses possible through increasing the entropy of the final output of a given classification model.

With current consideration a MNIST classification MLP, following is list of new defenses possible when attempting to increase the entropy of final output.


![image](https://user-images.githubusercontent.com/47445756/233807327-0cd0380f-0c22-40a9-87d1-f3218bcd7063.png)


It is well known that one needs to lookout for both utility, cost and effectiveness of a defense. Therefore, in terms of cost, following is the comparison of inference latency as compared to base model.

![image](https://user-images.githubusercontent.com/47445756/233807521-de27f7f7-82a3-46e6-b7fd-1739201effe4.png)


In terms of utility, following is the comparison of accuracy of base model, and defended model (refined model).

![image](https://user-images.githubusercontent.com/47445756/233807633-fedbf800-ee7f-4389-9f68-da584d6d0cb8.png)



In terms of effectiveness, following is the comparison of MIA attack AUC and attacker's advantage for above defenses. The results are evaluated using TF privacy, and the attacks considered are threshold based or shadow training based, where the attacker model is either logistic classifier, MLP or KNN classifer. Furthermore, the attack dataset includes the original dataset's training and validation data, so the attack premise is strong. The attack is evaluated over the whole dataset. For conciseness, only best attack AUC and advanatagec comaparison from these parameters are shown below.

![image](https://user-images.githubusercontent.com/47445756/233807766-4dbf4568-83db-47a3-a258-ca9bdd5631c4.png)

![image](https://user-images.githubusercontent.com/47445756/233807898-2804eb9c-8af6-4c6b-90e3-7617bfd9c48c.png)


By evaluating over cases: entire dataset, by class and by classification correctness, following is the comparison of TP vs FP plot.

![image](https://user-images.githubusercontent.com/47445756/233807990-56230a3d-b21c-4cf6-9183-5918b66a05ba.png)


Furthermore, following is the comparison plot of threshold, training and LiRA based evaluation of MIA over the defenses, by setting number of shadow models to 2. Probably the scores would be low, so increasing the number of shadow models would improve the scores.

![image](https://user-images.githubusercontent.com/47445756/233808070-f8e2f87c-9423-4f69-a2e8-543cc4bc4eb9.png)



