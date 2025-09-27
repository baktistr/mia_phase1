# Project phase1
FOR CMU 18734/17731 Project Phase1.

You are given:
 - a finetuned GPT2 model trained on data from [WikiText-103-raw-v1](https://huggingface.co/datasets/Salesforce/wikitext);
 - the test data composed of 1000 member and non-member text data;
 - the corresponding labels of test data for validating your attack.
 - a start kit, MIA_phase1 notebook, which provies all pre-processing and analysis functions except the attack function that you will need to implement.

**You are required to implement one of the three MIA attacks:**
 - Loss-based attack: you can use CrossEntropyloss or other losses you can come up with, based on the logits.
 - [Min-K attack](https://arxiv.org/pdf/2310.16789).
 - Zlib attack: calibrates loss with target sample x’s [zlib](https://docs.python.org/3/library/zlib.html) compression size: score(x) = loss(x) / zlib(x). You may also try other compression methods.

As your final deliverable, write a report with two sections:
 - Methodology [1-2 paragraphs]: What algorithm did you implement? Give a brief description of it and the formula if any.
 - Results [rest of the page]: 
What is the performance of your attack? (**AUC, TPR@0.01FPR, TPR@0.05FPR, ROC Curve Figure**). How does your attack efficacy depend on the hyperparameters of your selected MIA algorithm?
 - Code: attack code attached as Appendix.

There is no need to upload your notebook as you will be only implementing one of the simple attacks. You may try more if you are interested, which could also be helpful in the following phase, but you are only required to implement and report one.
