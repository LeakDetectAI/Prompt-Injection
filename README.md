# From ASR to ASP

## Abstract 

<div align="justify">

Recent studies demonstrate that Large Language Models (LLMs) are vulnerable to attacks that generate harmful or sensitive outputs. As open-source LLMs are increasingly adopted in high-impact applications such as finance, law, and healthcare, systematically investigating their security risks is becoming increasingly important towards trustworthy LLM era. This paper comprehensively studies effective prompt injection attacks against 14 widely used open-source and three closed-source LLMs on five attack benchmarks. Moreover, existing evaluation metrics mostly only consider the attack success rate, overlooking uncertainty in model responses. Our proposed Attack Success Probability (ASP) additionally captures uncertain behaviors for evaluation, where the model may initially refuse a harmful request but subsequently provide harmful guidance or vice versa, reflecting inconsistency and ambiguity in attack feasibility. By systematically analyzing the effectiveness of prompt injection attacks, we propose a straightforward and effective hypnotism attack; results show that this attack causes aligned language models, including Stablelm2, Mistral, Openchat, and Vicuna, to generate objectionable behaviors, achieving around 90% ASP. They also indicate that ignore prefix attacks can break all 14 open-source LLMs, achieving over 60% ASP on a multi-categorical dataset. We find that moderately well-known LLMs exhibit higher vulnerability to prompt injection attacks, highlighting the need to raise public awareness and prioritize efficient mitigation strategies. 
</div>

<!-- Warning: This paper may contain harmful offensive content. -->
## Overview

![](./data/attack.png)

## Setup and Scripts

### Install the [Ollama](https://ollama.com)

#### Download 13 evaluated LLMs using, for instance, `ollama run llama3`

#### Run `preprocess.py` to preprocess simple datasets such as [AdvBench](https://github.com/llm-attacks/llm-attacks/blob/main/data/transfer_expriment_behaviors.csv)

#### Run `moderation.py` to see the harmfulness score evaluated by the OpenAI `text-moderation-007`

#### Run the following scripts for different prompt injection attack methods:

1. Script for running ignore prefix attacks:

```
chmod +x run_attack_ignore.sh
./run_attack_ignore.sh 
```

2. Script for running role-playing CoT attacks:

```
chmod +x run_attack_role.sh
./run_attack_role.sh 
```

3. Script for running Hypnotism attacks:

```
chmod +x run_attack_hypnotism.sh
./run_attack_hypnotism.sh 
```
#### Run `ollama.py` to see the ASP for downloaded open-source LLMs

#### Run `asp.py` for the automatic evaluation


## Citation

If you use this work, please cite:

```bibtex
@misc{wang2026asraspevaluatingprompt,
      title={From ASR to ASP: Evaluating Prompt Attack Vulnerabilities Against Open-Source LLMs}, 
      author={Jiawen Wang and Pritha Gupta and Ivan Habernal and Eyke Hüllermeier and Xiaoxue Gao and Nancy F. Chen},
      year={2026},
      eprint={2505.14368},
      archivePrefix={arXiv},
      primaryClass={cs.CR},
      url={https://arxiv.org/abs/2505.14368}, 
}
```

