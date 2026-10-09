# LUFFY Development Repository

> 🚧 **Development Branch** - This is the main development repository for LUFFY (Learning to Reason Under Off‑Policy Guidance)

## About LUFFY

LUFFY is a reinforcement learning framework that bridges the gap between zero-RL and imitation learning by incorporating off-policy reasoning traces into the training process. This repository contains the core implementation and development work.

## 🔧 Development Status

This repository is under active development. Many features are currently being implemented or need refactoring.

## 🚀 Quick Start

⚠️ **Note**: This development version has incomplete implementations. Many features are marked as TODO and need to be completed before production use.

```bash
# Clone the repository
git clone <repository-url>
cd LUFFY

# Install dependencies
pip install -r luffy/requirements.txt

# Note: Some functionality is incomplete - check TODO list below for details
```

## 📁 Repository Structure

```
LUFFY/
├── luffy/                 # Core framework
│   ├── deepscaler/        # Scaling utilities (OpenAI integration implemented; Gemini still needs API integration)
│   ├── verl/              # RL training components (⚠️ Some features incomplete)
│   └── ...
├── data/                  # Training data and scripts
├── eval_scripts/          # Evaluation utilities
├── exp_scripts/           # Experiment scripts
└── README.md              # This file
```

## ⚠️ Development Notes

- This is a **development version** with incomplete implementations
- Many functions contain TODO markers indicating pending work
- OpenAI API integration is implemented, but Gemini/Vertex AI integration is still a placeholder
- FSDP and distributed training features need completion


### 🔴 High Priority TODOs

- **API Integration**: Gemini/Vertex AI implementation still needs completion
- **Reward System**: Parallel processing and validation for reward computation  
- **FSDP Training**: Model loading and distributed training setup
- **Data Processing**: Remaining tensor reshaping optimizations and validation improvements


### 📝 Complete TODO List

- [x] ~~**luffy/deepscaler/utils.py:45** - Implement OpenAI API client initialization~~
- [x] ~~**luffy/deepscaler/utils.py:46** - Add proper authentication handling~~
- [x] ~~**luffy/deepscaler/utils.py:47** - Implement exponential backoff retry logic for rate limits~~
- [x] ~~**luffy/deepscaler/utils.py:48** - Add comprehensive error handling for different API errors~~
- [x] ~~**luffy/deepscaler/utils.py:49** - Implement response parsing and validation~~
- [ ] **luffy/deepscaler/utils.py:50** - Add logging for API calls and errors
- [ ] **luffy/deepscaler/utils.py:51** - Support batch processing for multiple prompts
- [ ] **luffy/deepscaler/utils.py:52** - Add timeout configuration for API calls
- [ ] **luffy/deepscaler/utils.py:88** - Implement Vertex AI initialization and authentication
- [ ] **luffy/deepscaler/utils.py:89** - Configure safety settings for content generation
- [ ] **luffy/deepscaler/utils.py:90** - Set up GenerativeModel with proper system instructions
- [ ] **luffy/deepscaler/utils.py:91** - Implement retry logic with exponential backoff
- [ ] **luffy/deepscaler/utils.py:92** - Add comprehensive error handling for API access issues
- [ ] **luffy/deepscaler/utils.py:93** - Handle rate limiting and quota management
- [ ] **luffy/deepscaler/utils.py:94** - Implement response validation and text extraction
- [ ] **luffy/deepscaler/utils.py:95** - Add support for different generation configurations
- [ ] **luffy/test.py:1590** - add smaller page sizes when https://github.com/Dao-AILab/flash-attention/pull/824 is merged
- [ ] **luffy/verl/examples/split_placement/split_monkey_patch.py:141** - make a canonical logger that supports various backend
- [ ] **luffy/verl/tests/e2e/check_results.py:21** - this function needs error handling
- [ ] **luffy/verl/tests/model/test_transformer.py:22** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformer.py:50** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformer.py:111** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:34** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:81** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:159** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/ray/test_high_level_scheduling_api.py:25** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/tests/ray/test_worker_group_basics.py:43** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:54** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:83** - it seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:123** - (zhangchi.usc1992): 1. support create from random initialized model. 2. Support init with FSDP directly
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:199** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:207** - add transformer policy
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:226** - add more optimizer args into config
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:252** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:263** - a sharding manager that do nothing?
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:391** - here, we should return all metrics
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:517** - support DCP and save sharded checkpoints
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:90** - add other ways to estimate advantages
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:168** - support each role have individual ray_worker_group_cls,
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:293** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:599** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:637** - add response length
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:63** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:437** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:592** - check path
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:628** - from remote not implemented yet
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_attention.py:380** - llama does not have dropout in the config??
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:78** - add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:86** - add sequence parallel operator all_gather here
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:90** - add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:330** - for better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:588** - for better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/registry.py:21** - (sgm): HF may supported more than listed here, we should add more after testing
- [ ] **luffy/verl/verl/models/transformers/llama.py:88** - These transpose are quite inefficient but Flash Attention requires the layout [batch_size, sequence_length, num_heads, head_dim]. We would need to refactor the KV cache
- [x] ~~**luffy/verl/verl/protocol.py:114** - Implement batch dimension folding for efficient processing~~
- [x] ~~**luffy/verl/verl/protocol.py:115** - Add validation for batch size compatibility~~
- [x] ~~**luffy/verl/verl/protocol.py:116** - Handle edge cases where batch_size is not divisible by new_batch_size~~
- [ ] **luffy/verl/verl/protocol.py:117** - Optimize memory usage during tensor reshaping
- [ ] **luffy/verl/verl/protocol.py:118** - Add support for different tensor types and shapes
- [x] ~~**luffy/verl/verl/protocol.py:131** - Implement batch dimension unfolding functionality~~
- [x] ~~**luffy/verl/verl/protocol.py:132** - Add support for variable batch dimensions~~
- [ ] **luffy/verl/verl/protocol.py:133** - Optimize tensor view operations for performance
- [x] ~~**luffy/verl/verl/protocol.py:134** - Handle non-tensor batch data reshaping properly~~
- [ ] **luffy/verl/verl/protocol.py:135** - Add error handling for invalid batch dimensions
- [ ] **luffy/verl/verl/protocol.py:156** - (zhangchi.usc1992) add consistency check
- [ ] **luffy/verl/verl/protocol.py:252** - we can actually lift this restriction if needed
- [ ] **luffy/verl/verl/protocol.py:338** - (zhangchi.usc1992) whether to copy
- [ ] **luffy/verl/verl/single_controller/ray/base.py:439** - create a class with customizable name
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/arg_utils.py:64** - (shengguangming): delete the unused args
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/arg_utils.py:147** - (woosuk): Support fine-grained seeds (e.g., seed per request).
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:237** - (shengguangming): maybe we can hack the autoregressive logics without only ...
