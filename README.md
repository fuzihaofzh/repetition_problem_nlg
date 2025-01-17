# A Theoretical Analysis of the Repetition Problem in Text Generation
This repository share the code for the paper "A Theoretical Analysis of the Repetition Problem in Text Generation" in AAAI 2021. The repetition problem has been observed in nearly all text generation models. We theoretically prove that this problem is, unfortunately, caused by the traits of our language itself. There exists too many words predicting the same word as the subsequent word with high probability. Consequently, it is easy to go back to that word and form repetitions. 
We dub this problem as the **high inflow problem**. Based on the theoretical analysis, we propose a novel **rebalanced encoding** approach to alleviate the high inflow problem.

[[Paper]](https://ojs.aaai.org/index.php/AAAI/article/view/17520/17327)
[[Slides]](https://github.com/fuzihaofzh/repetition-problem-nlg/blob/main/aaai21-repetition.pdf)
[[Video]](https://slideslive.com/38948354/a-theoretical-analysis-of-the-repetition-problem-in-text-generation)
[[arXiv Paper with Appendix]](https://arxiv.org/pdf/2012.14660.pdf)


<p class="aligncenter">
<img src="https://user-images.githubusercontent.com/1419566/103292227-5fb86780-4a28-11eb-97c5-44ace9e0f6cb.png" width="75%"  />
</p>

## Requirements
- GCC >= 4.8
- Python >= 3.7

## Install 
```bash
git clone https://github.com/fuzihaofzh/repetition-problem-nlg.git
cd repetition-problem-nlg
./scripts/setup.sh
```

## iwslt14
### Preprocess Data
```bash
./scripts/iwslt14_preprocess.sh
```
### Train
```bash
./scripts/iwslt14_train.sh iwslt14deen_fastbpe_10000
./scripts/iwslt14_train.sh iwslt14deen_fastbpe_10000_re0.1
```

### Test
```bash
./scripts/iwslt14_test.sh
```
Results can be found in `output/eval/*`


## wiki103
### Download the preprocessed data
```bash
git clone https://github.com/fuzihaofzh/preprocessed_wiki103.git output/preprocessed/wiki103
```
This may take few minutes to complete.

### Preprocess Data
```bash
./scripts/wiki103_preprocess.sh
```
### Train
```bash
./scripts/wiki103_train.sh wiki103_fastbpe_10000
./scripts/wiki103_train.sh wiki103_fastbpe_10000_re0.1
```

### Test
```bash
./scripts/wiki103_test.sh
```
Results can be found in `output/eval/*`



## Cite 
```latex
@inproceedings{fu2020a,
  title={A Theoretical Analysis of the Repetition Problem in Text Generation.},
  author={Fu, Zihao and Lam, Wai and So, Anthony Man-Cho and Shi, Bei },
  booktitle={Thirty-Fifth AAAI Conference on Artificial Intelligence},
  year={2021}
}
```
