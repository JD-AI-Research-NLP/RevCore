# RevCore
***ACL-Findings 2021 RevCore: Review-argmented Conversational Recommendation***

Existing conversational recommendation (CR) systems normally suffer from insufficient item information when conducted on short dialogue history and unfamiliar items.
Incorporating external information (e.g., reviews) is a potential solution to alleviate this problem.
Given that reviews often provide rich and detailed user experience on different factors of interest, they are potential ideal resources for providing high-quality recommendations within an informative conversation.

![image](https://github.com/JD-AI-Research-NLP/RevCore/blob/main/method_final_1.png)

We design a novel end-to-end framework, namely, Review-augmented Conversational Recommender (\textbf{RevCore}), where reviews are seamlessly incorporated to enrich item information and assist generating both coherent and informative responses.
Particularly, in RevCore, we extract sentiment-consistent reviews, perform review-enriched and entity-based recommendations for item suggestions, as well as use a review-attentive encoder-decoder for response generation.

(To-Do)
# Environment 
pytorch==1.3.0, torch_geometric==1.3.2

To be honest, most of errors derive from the wrong installation of the two packages

# Notation
The word embedding file **word2vec_redial.npy** can be produced by the following function dataset.prepare_word2vec(), or directly download from the google netdisk https://drive.google.com/file/d/1BzwGgbUBilaEZXAu7e1SlvxSwcAfVe2w/view?usp=sharing, ***Chinese friends need VPN to download this file***.

# Training
This model is trained by two steps, you should run the following code to pre-train the parameters by Mutual Information Maximization and then learn the recommendation task. Based on my experience, it will converge after 3 epochs pre-training and 3 epochs fine-tuning.

```python run.py```

Then you can run the following code to learn the conversation task. Limitted by the small dataset, Transformer model is difficult to coverge, so our model need many of epochs to covergence. Please be patient to train this model.

```python run.py --is_finetune True```

For convenience, our model will report the result on test data automatically after covergence.

# Thanks for your citation
```c
@inproceedings{DBLP:conf/kdd/ZhouZBZWY20,
  author    = {Kun Zhou and
               Wayne Xin Zhao and
               Shuqing Bian and
               Yuanhang Zhou and
               Ji{-}Rong Wen and
               Jingsong Yu},
  title     = {Improving Conversational Recommender Systems via Knowledge Graph based
               Semantic Fusion},
  booktitle = {{KDD} '20: The 26th {ACM} {SIGKDD} Conference on Knowledge Discovery
               and Data Mining, Virtual Event, CA, USA, August 23-27, 2020},
  pages     = {1006--1014},
  year      = {2020},
  url       = {https://dl.acm.org/doi/10.1145/3394486.3403143}
}
```
