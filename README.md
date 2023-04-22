# entropic_MIA_defense

This repo is study of the significance of entropy of the classification vector of a classification model, in relationship to membership inference attack (MIA), as specified in this paper: He, Xinlei, et al. "Membership-Doctor: Comprehensive Assessment of Membership Inference Against Machine Learning Models." arXiv preprint arXiv:2208.10445 (2022).

More specifically, this repo tries to compare several variations of defenses possible through increasing the entropy of the final output of a given classification model.

With current consideration a MNIST classification MLP, following is list of new defenses possible when attempting to increase the entropy of final output.



![image](https://user-images.githubusercontent.com/47445756/233807327-0cd0380f-0c22-40a9-87d1-f3218bcd7063.png)
