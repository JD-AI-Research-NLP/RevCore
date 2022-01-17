# RevCore
***ACL-Findings 2021 RevCore: Review-augmented Conversational Recommendation***

Existing conversational recommendation (CR) systems normally suffer from insufficient item information when conducted on short dialogue history and unfamiliar items.
Incorporating external information (e.g., reviews) is a potential solution to alleviate this problem.
Given that reviews often provide rich and detailed user experience on different factors of interest, they are potential ideal resources for providing high-quality recommendations within an informative conversation.

![image](https://github.com/JD-AI-Research-NLP/RevCore/blob/main/method_final_1.png)

We design a novel end-to-end framework, namely, Review-augmented Conversational Recommender (RevCore), where reviews are seamlessly incorporated to enrich item information and assist generating both coherent and informative responses.
Particularly, in RevCore, we extract sentiment-consistent reviews, perform review-enriched and entity-based recommendations for item suggestions, as well as use a review-attentive encoder-decoder for response generation.

(To-Do)

# Environment 
pytorch==1.7.0, torch_geometric==2.0.1,
cuda==11.0 


# Training
This model is trained by two steps, you should run the following code to learn the recommendation task.

```python run_train_test_copy.py```

Then you can run the following code to learn the conversation task. Limitted by the small dataset, Transformer model is difficult to coverge, so our model need many of epochs to covergence. Please be patient to train this model.

```python run_train_test_copy.py --is_finetune True```

For convenience, our model will report the result on test data automatically after covergence.


# Thanks for your citation
```c
@inproceedings{Lu-etal-2021-RevCore,
    title = "RevCore: Review-argmented Conversational Recommendation",
    author = "Lu, Yu  and
    Bao, Junwei and
    Song, Yan  and
    Ma, Zichen  and
    Cui, Shuguang  and
    Wu, Youzheng  and
    He, Xiaodong",
    booktitle = "Findings of the Association for Computational Linguistics: ACL-IJCNLP 2021",
    year = "2021",
}
```


