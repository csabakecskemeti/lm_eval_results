# lm_eval_results
2025 | [DevQuasar.com](http://devquasar.com)
Note: the repository require [git LFS](https://git-lfs.com/) 

Evaluations perfomed on local server (2xV100) using [EleutherAI/lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness).

By default the Open LLM Leaderboard's standard tests are performed:
- hellaswag
- leaderboard_gpqa
- leaderboard_ifeval
- leaderboard_math_hard
- leaderboard_mmlu_pro
- leaderboard_musr
- leaderboard_bbh

To replicate, use command
`accelerate launch -m  lm_eval --model hf  --model_args pretrained=meta-llama/Llama-3.1-8B-Instruct,parallelize=True,dtype="float16" --tasks hellaswag,leaderboard_gpqa,leaderboard_ifeval,leaderboard_math_hard,leaderboard_mmlu_pro,leaderboard_musr,leaderboard_bbh  --batch_size auto:4 --log_samples   --output_path eval_results`
