# Enhancing Editorial Tasks: A Case Study on Rewriting Customer Help Page Contents Using Large Language Models

We introduce a German-language dataset comprising Frequently Asked Question-Answer pairs: raw FAQ drafts, their revisions by professional editors and LLM generated revisions. The data was used to investigate the use of large language models (LLMs) to enhance the editorial process of rewriting customer help pages. 

The input data was provided by Deutsche Telekom AG (DT), a large German telecommunications company. The corpus comprises 56 question-answer pairs addressing potential customer inquiries across various topics, including additional SIM cards, Netflix subscriptions, relocation, changing mobile service providers, house connection orders, hardware order and delivery status, and fixed-line internet and TV setup. For each FAQ pair, a raw input is provided by specialized departments, and a rewritten gold output is crafted by a professional editor of DT. The final dataset also includes LLM generated FAQ-pairs.

On this dataset, we evaluate the performance of four large language models (LLM) through diverse prompts tailored for the rewriting task. We conduct automatic evaluations of content and text quality using ROUGE, BERTScore, and ChatGPT.
Furthermore, we let professional editors assess the helpfulness of automatically generated FAQ revisions for editorial enhancement. Our findings indicate that LLMs can produce FAQ reformulations beneficial to the editorial process. We observe minimal performance discrepancies among LLMs for this task, and our survey on helpfulness underscores the subjective nature of editors' perspectives on editorial refinement.

For detailed results, please see our paper accepted at [INLG 20204, Tokyo, Japan](https://inlg2024.github.io/) (see also [Citation](#-citation)).

## 📝 &nbsp; Data format

The data is provided in json format. 

The folder [data/faq-data](data/faq-data) contains raw FAQ drafts (input field), revisions by professional editors (reference field), and up to 3 LLM-generated revisions for each input (predictions field). The json also contains scores for each prediction (BERTScore, Rouge and ChatGPT-4 Scores wrt. hallucination, informativeness and coherence. At the end of the files there are also overall average scores for each metric.

### Data fields
- `instances`: list of evaluated instances
- `prompt_id`: a `string` feature specifying the LLM, prompt, and task type
- `description`: a `string` feature
- `prompt_type`: a `string` feature,
- `system_prompts`: a `string` feature giving the generic system prompt
- `user_prompts`: the list of user prompts, one per instance
- `requests`: a list of request parameters, one per instance
- `responses`: the list of raw response information, one per instance

Each `instance` contains the following fields:
- `instance_id`: instance identifier, a `string` feature.
- `input`: the draft / input texts of an FAQ entry, consisting of a reference `url` field (a `string` feature), a `question` (`string` feature) and an `answer` (`string` feature)
- `predictions`: a list of up to 3 predictions (generated rewrites) of the input for this LLM. Each prediction consists of an `idx` (`int` feature) field, plus a generated `question` (`string` feature) and `answer` (`string` feature). Each prediction also contains a list of `evaluation` scores (content overlap metrics like `ROUGE`, and GPT4-based evaluations such as `hallucinations`). 
- `reference`: the human-written reference FAQ, consisting of a `question` (`string` feature) and `answer` (`string` feature), and a `url` (`string` feature) reference
- `use_case`: a `string` feature describing the general topic of the FAQ instance

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



