# <img src="assets/nocha2.png" alt="NoCha" width="150" height="40"> 
[![arXiv](https://img.shields.io/badge/arXiv-2406.16264-b31b1b.svg)](https://arxiv.org/abs/2406.16264)

`Paper:` ["One Thousand and One Pairs: A "novel" challenge for long-context language models"](https://arxiv.org/abs/2406.16264)

`Authors:` Marzena Karpinska, Katherine Thai, Kyle Lo, Tanya Goyal, Mohit Iyyer

`Leaderboard:` [Nocha Leaderboard](https://novelchallenge.github.io/index.html)

`TL'DR:` NoCha is a dataset for evaluation loooong context language models' abilities to reason over book-length context. We do NOT release the entire dataset as it contrains new, i.e. copyrighted, books. Instead, we release a sample data build on classic novels and commit to evaluate LMs on the entire dataset ourselves.

## About Nocha

Nocha is a dataset designed to test the abilities of long-context language models to efficiently process book-level input. The model is presented with a claim about a fictional book along with the book text as the context and its task is to validate the claim as either true or false based on the context provided. The test data consists of true/false narrative minimal pairs about the same event or character (see example below). Each false claims differs from its paired true claim _only_ by the inclusion of false information regarding the same event or entity. The model must verify both claims in a pair to be awarded one point. The accuracy is then calculated on the pair level, by counting the number of correctly identified pairs and dividing it by the total pairs processed by the model.

This approach allows has several advantages:

🪄  It allows us to better control the quality of created claims by comparing the true claim with the false claim and identifying claims which are too similar (i.e., the false claim could be true) or subjective;

🪄  It protects from awarding the model for "being right for the wrong reason" as the model has to identify both claims in the pair correctly in order to be awarded one point.

We also measure human accuracy on a subset of our claim pairs and confirm the in ~97% of cases human annotators who have read the books are able to correctly identify _both_ claims in the pair.


## Sample Data

We do NOT release our full dataset as (1) it contains mostly books published in 2023/2024 and hence under copyrights, and (2) we want to prevent model providers from training on the labeled data compromising the dataset. Instead, we annotated also four classic novels, which we provide as a sample of our dataset. 

```json
{
      "book_title": "little_women_louisa_may_alcott",
      "lenght": 235118,
      "lenght_bucket": "above 180k",
      "genre": "historical",
      "publication_year": "classics",
      "type": "True",
      "claim": "Mr. and Mrs. March originally object to Mr. Bhaer because he is too old and not rich enough.",
      "response-gemini": "<explanation>While the statement mentions concerns that are common in families, the text does not state that Mr. and Mrs. March object to Mr. Bhaer. In fact, they seem to like him from the start. Aunt March is the one who objects to the match because of his lack of wealth. </explanation><answer>FALSE</answer>",
      "response-{model}": "..."
}
```

Data info: TODO

### Corpus Statistics

|              | **Books**                   | **Books**                   | **Claim** {*pairs*}           | **Claim**  {*pairs*}          | **Claim**  {*pairs*}                   |
|--------------|-----------------------------|-----------------------------|-------------------------------|-------------------------------|-------------------------------|
|              | (*n=67*)                    | (*n=67*)                    | (*n=2002*){*1001*}           | (*n=2002*){*1001*}             | (*n=2002*){*1001*}            |
|              | **Tokens**                  | **Words**                   | **Tokens**                    | **Words**                     | **# Claim/Book**              |
| **Mean**     | 127,324                     | 98,587                      | 23.22                         | 18.26                         | 14.94                         |
| **St. Dev.** | 52,561                      | 39,506                      | 7.62                          | 6.49                          | 8.37                          |
| **Max**      | 336,288                     | 257,445                     | 63                            | 57                            | 46                            |
| **Min**      | 49,156                      | 38,023                      | 5                             | 4                             | 4                             |




## Citation Information
If you use this work in any form, please cite as:
```
@misc{nocha-2024-karp-thai-et-al,
      title={One Thousand and One Pairs: A "novel" challenge for long-context language models}, 
      author={Marzena Karpinska and Katherine Thai and Kyle Lo and Tanya Goyal and Mohit Iyyer},
      year={2024},
      eprint={https://arxiv.org/abs/2406.16264},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
