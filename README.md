# Does External Knowledge Help Explainable Natural Language Inference?
This repository contains the collected human ratings of textual explanation quality presented in our BlackboxNLP 2021 paper
[Does External Knowledge Help Explainable Natural Language Inference? Automatic Evaluation vs. Human Ratings](https://aclanthology.org/2021.blackboxnlp-1.3/).

## Data
Our data contains 4000 human ratings of model-predicted labels and explanations.
Each instance covers ratings of label correctness, explanation correctness, grammatical correctness as well as commonsense inclusion.

You can load the TSV file using, e.g., pandas:
```python
import pandas as pd
ratings = pd.read_csv('ratings.tsv', sep='\t')
print(ratings)
```

The data contains the following columns:
* **model**: The model that is used to predict the label and generate the explanation (includes 'comet', 'comet_continuous', 'continuous', 'filtered_ensemble', 'gpt_2_lf', 'ground_truth', 'vanilla' and 'wt5').
* **batch_number**: Experiment batch number.
* **within_batch_id**: ID within the experiment batch.
* **pairID**: ID of the premise-hypothesis pair used in the e-SNLI dataset.
* **premise**: Premise sentence.
* **hypothesis**: Hypothesis sentence.
* **gt_label**: Ground truth NLI label annotation ('contradiction', 'entailment' or 'neutral').
* **gt_expl**: Ground truth explanation sentence.
* **commonsense_level**: Annotation of the level of required external knowledge to solve the NLI task.
* **pred_label**: Model prediction of the label ('contradiction', 'entailment' or 'neutral').
* **pred_expl**: Model prediction of the explanation.
* **rating_label**: Human rating of label correctness ('correct' or 'wrong').
* **rating_expl**: Human rating of explanation correctness ('correct' or 'wrong').
* **rating_grammar**: Human rating of grammar correctness ('correct' or 'wrong').
* **rating_commonsense**: Human rating of grammar correctness ('no', 'no_need' or 'yes').
* **anonymized_worker_id**: Anonymized worker ID.
* **completion_time**: Completion time of the experiment batch in minutes (per worker).

For further details, we refer to [our paper](https://aclanthology.org/2021.blackboxnlp-1.3/).


## License
The collected ratings are licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) (CC-BY-4.0).
## Citation
If you use our models, scores or data in your work, please cite [our paper](https://aclanthology.org/2021.blackboxnlp-1.3/).
```
@inproceedings{schuff-etal-2021-external,
    title = "Does External Knowledge Help Explainable Natural Language Inference? Automatic Evaluation vs. Human Ratings",
    author = "Schuff, Hendrik  and
      Yang, Hsiu-Yu  and
      Adel, Heike  and
      Vu, Ngoc Thang",
    booktitle = "Proceedings of the Fourth BlackboxNLP Workshop on Analyzing and Interpreting Neural Networks for NLP",
    month = nov,
    year = "2021",
    address = "Punta Cana, Dominican Republic",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.blackboxnlp-1.3",
    pages = "26--41",
    abstract = "Natural language inference (NLI) requires models to learn and apply commonsense knowledge. These reasoning abilities are particularly important for explainable NLI systems that generate a natural language explanation in addition to their label prediction. The integration of external knowledge has been shown to improve NLI systems, here we investigate whether it can also improve their explanation capabilities. For this, we investigate different sources of external knowledge and evaluate the performance of our models on in-domain data as well as on special transfer datasets that are designed to assess fine-grained reasoning capabilities. We find that different sources of knowledge have a different effect on reasoning abilities, for example, implicit knowledge stored in language models can hinder reasoning on numbers and negations. Finally, we conduct the largest and most fine-grained explainable NLI crowdsourcing study to date. It reveals that even large differences in automatic performance scores do neither reflect in human ratings of label, explanation, commonsense nor grammar correctness.",
}
```
