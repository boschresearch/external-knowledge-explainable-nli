# Does External Knowledge Help Explainable Natural Language Inference?
This repository contains the collected human ratings of textual explanation quality presented in our BlackboxNLP 2021 paper
[Does External Knowledge Help Explainable Natural Language Inference? Automatic Evaluation vs. Human Ratings](https://arxiv.org/abs/2109.07833).

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

For further details, we refer to [our paper](https://arxiv.org/abs/2109.07833).


## License
The collected ratings are licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) (CC-BY-4.0).
## Citation
If you use our models, scores or data in your work, please cite [our paper](https://arxiv.org/abs/2109.07833).

Temporary Bibtex citation (until the EMNLP 2021 proceedings are published):
```
@misc{schuff2021does,
      title={Does External Knowledge Help Explainable Natural Language Inference? Automatic Evaluation vs. Human Ratings}, 
      author={Hendrik Schuff and Hsiu-Yu Yang and Heike Adel and Ngoc Thang Vu},
      year={2021},
      eprint={2109.07833},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
