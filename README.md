# Enhancing Editorial Tasks: A Case Study on Rewriting Customer Help Page Contents Using Large Language Models

We introduce a German-language dataset comprising Frequently Asked Question-Answer pairs: raw FAQ drafts, their revisions by professional editors and LLM generated revisions.

The input data was provided by Deutsche Telekom AG (DT), a large German telecommunications company. The corpus comprises 56 question-answer pairs addressing potential customer inquiries across various topics, including additional SIM cards, Netflix subscriptions, relocation, changing mobile service providers, house connection orders, hardware order and delivery status, and fixed-line internet and TV setup. For each FAQ pair, a raw input is provided by specialized departments, and a rewritten gold output is crafted by a professional editor of DT. The final dataset also includes LLM generated FAQ-pairs.

On this dataset, we evaluate the performance of four large language models (LLM) through diverse prompts tailored for the rewriting task. We conduct automatic evaluations of content and text quality using ROUGE, BERTScore, and ChatGPT.
Furthermore, we let professional editors assess the helpfulness of automatically generated FAQ revisions for editorial enhancement. Our findings indicate that LLMs can produce FAQ reformulations beneficial to the editorial process. We observe minimal performance discrepancies among LLMs for this task, and our survey on helpfulness underscores the subjective nature of editors' perspectives on editorial refinement.

For detailed results, please see our paper accepted at [INLG 20204, Tokyo, Japan](https://inlg2024.github.io/) (see also [Citation](#-citation)).

## 📝 &nbsp; Data format

The data is provided in json format. 

The folder [data/faq-data](data/faq-data) contains raw FAQ drafts (input field), revisions by professional editors (reference field), and up to 3 LLM-generated revisions for each input (predictions field). The json also contains scores for each prediction (BERTScore, Rouge and ChatGPT-4 Scores wrt. hallucination, informativeness and coherence. At the end of the files there are also overall average scores for each metric.

The folder [data/prompts](data/prompts) contains an overview of the prompts.


## 📚&nbsp; Citation

If you use the dataset, please cite the following paper:
```
@inproceedings{pub15191,
    author = {Gabryszak, Aleksandra and Röder, Daniel and Binder, Arne Björn and Sion, Luca and Hennig, Leonhard},
    title = {Enhancing Editorial Tasks: A Case Study on Rewriting Customer Help Page Contents Using Large Language Models},
    booktitle = {Proceedings of the 17th International Natural Language Generation Conference. International Natural Language Generation Conference (INLG-2024), Tokyo, Japan},
    year = {2024},
    publisher = {Association for Computational Linguistics}
}
```

## 📘&nbsp; License
The data is released under the terms of the [CC-BY-SA-4.0](LICENCE.txt).



