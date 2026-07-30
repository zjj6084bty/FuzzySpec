# FuzzySpec



## Introduction

 FuzzySpec breaks the traditional paradigm of decoupled retrieval and verification, and achieves synergistic optimization of speculative decoding inference performance by integrating fuzzy retrieval and elastic verification strategies. FuzzySpec improves the recall of long matches by introducing an adaptive fuzzy retrieval mechanism with edit distance constraints, and constructs a dynamic elastic verification mechanism based on retrieval confidence and target model prediction entropy, ensuring generation quality while improving inference speed. 



## Prepare retrieval source
First, you need to download alpaca-cleaned, python_code_instructions_18k_alpaca, and gsm8k from [sam_data](https://drive.google.com/file/d/1N7FARwsGQXIbL_3B2uEYh3CkDh4Bc6it/view) and place them in the 'datastore/sam_data' directory. Then, execute the following command:
```bash
cd datastore
sh question_to_model_answer.sh
sh build_sam.sh
```


## Inference

```bash
cd llm_judge
sh run_baseline.sh #运行自回归解码
sh run_fuzzyspec.sh
sh caculate_gen_quality.sh #评估生成质量
```

## Acknowledgements
The codebase is from [SAM-decoding](https://github.com/hyx1999/SAM-Decoding/tree/main) and influenced by remarkable projects from the LLM community, including [FastChat](https://github.com/lm-sys/FastChat), [vllm](https://github.com/vllm-project/vllm) and many others.

