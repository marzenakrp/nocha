# nocha

This it the official repo for "One Thousand and One Pairs: A "novel" challenge for long-context language models"

`Authors:` Marzena Karpinska, Katherine Thai, Kyle Lo, Tanya Goyal, Mohit Iyyer

`Leaderboard:` [Nocha Leaderboard](https://novelchallenge.github.io/index.html)

## About Nocha

Nocha is a dataset designed to test the abilities of long-context language models to efficiently process book-level input. The model is presented with a claim about a fictional book along with the book text as the context and its task is to validate the claim as either true or false based on the context provided. The test data consists of true/false narrative minimal pairs about the same event or character (see example below). Each false claims differs from its paired true claim _only_ by the inclusion of false information regarding the same event or entity. The model must verify both claims in a pair to be awarded one point. The accuracy is then calculated on the pair level, by counting the number of correctly identified pairs and dividing it by the total pairs processed by the model.

This approach allows has several advetages:

- It allows us to better control the quality of created claims by comparing the true claim with the false claim and identifying claims which are too similar (i.e., the false claim could be true) or subjective;
- It protects from awarding the model for "being right for the wrong reason" as the model has to identify both claims in the pair correctly in order to be awarded one point.

We also measure human accuracy on our claim pairs and confirm the in ~97% of cases human annotators who have read the books are able to correctly identify _both_ claims in the pair.


## Sample Data

We do NOT release our full dataset as (1) it contains mostly books published in 2023/2024 and hence under copyrights, and (2) we want to prevent model providers from training on the labeled data compromising the dataset. Instead, we annotated also four classic novels, which we provide as a sample of our dataset. 


## Citation Information
If you use this work in any form, please cite as:
```
@misc{nocha-2024-karp-thai-et-al,
      title={One Thousand and One Pairs: A "novel" challenge for long-context language models}, 
      author={Marzena Karpinska and Katherine Thai and Kyle Lo and Tanya Goyal and Mohit Iyyer},
      year={2024},
      eprint={},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
