# vllm

  

curl -LsSf https://astral.sh/uv/install.sh | sh

source $HOME/.cargo/env

  

sudo apt install python3 python3-pip

uv venv --python 3.12 --seed

source .venv/bin/activate

source .venv/bin/activate && uv pip install "vllm[audio]"

uv pip install vllm --torch-backend=auto

source .venv/bin/activate && vllm serve openai/whisper-large-v3 --host 0.0.0.0 --port 8000 --gpu-memory-utilization 0.85

## Log 
rechenknecht@rechenknecht:/mnt/c/src/github/wirus_bb_main/vllmWhisper$  source .venv/bin/activate && vllm serve openai/whisper-large-v3 --host 0.0.0.0 --port 8000 --gpu-memory-utilization 0.85
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:325] 
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:325]        █     █     █▄   ▄█
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:325]  ▄▄ ▄█ █     █     █ ▀▄▀ █  version 0.15.1
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:325]   █▄█▀ █     █     █     █  model   openai/whisper-large-v3
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:325]    ▀▀  ▀▀▀▀▀ ▀▀▀▀▀ ▀     ▀
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:325] 
(APIServer pid=11980) INFO 02-12 19:33:39 [utils.py:261] non-default args: {'model_tag': 'openai/whisper-large-v3', 'api_server_count': 1, 'host': '0.0.0.0', 'model': 'openai/whisper-large-v3', 'gpu_memory_utilization': 0.85}
(APIServer pid=11980) INFO 02-12 19:33:40 [model.py:541] Resolved architecture: WhisperForConditionalGeneration
(APIServer pid=11980) INFO 02-12 19:33:40 [model.py:1561] Using max model len 448
(APIServer pid=11980) INFO 02-12 19:33:40 [model.py:575] Encoder-decoder model detected, disabling mm processor cache.
(APIServer pid=11980) INFO 02-12 19:33:41 [scheduler.py:217] Encoder-decoder models do not support chunked prefill nor prefix caching; disabling both.
(APIServer pid=11980) INFO 02-12 19:33:41 [vllm.py:624] Asynchronous scheduling is enabled.
(APIServer pid=11980) INFO 02-12 19:33:41 [vllm.py:751] Encoder-decoder models do not support FULL_AND_PIECEWISE. Overriding cudagraph_mode to FULL_DECODE_ONLY.
(APIServer pid=11980) WARNING 02-12 19:33:41 [vllm.py:905] No piecewise cudagraph for executing cascade attention. Will fall back to eager execution if a batch runs into cascade attentions.
(APIServer pid=11980) WARNING 02-12 19:33:44 [interface.py:470] Using 'pin_memory=False' as WSL is detected. This may slow down the performance.
(EngineCore_DP0 pid=12321) INFO 02-12 19:34:53 [core.py:96] Initializing a V1 LLM engine (v0.15.1) with config: model='openai/whisper-large-v3', speculative_config=None, tokenizer='openai/whisper-large-v3', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.float16, max_seq_len=448, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, enable_return_routed_experts=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser='', reasoning_parser_plugin='', enable_in_reasoning=False), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None, kv_cache_metrics=False, kv_cache_metrics_sample=0.01, cudagraph_metrics=False, enable_layerwise_nvtx_tracing=False, enable_mfu_metrics=False, enable_mm_processor_stats=False, enable_logging_iteration_details=False), seed=0, served_model_name=openai/whisper-large-v3, enable_prefix_caching=False, enable_chunked_prefill=False, pooler_config=None, compilation_config={'level': None, 'mode': <CompilationMode.VLLM_COMPILE: 3>, 'debug_dump_path': None, 'cache_dir': '', 'compile_cache_save_format': 'binary', 'backend': 'inductor', 'custom_ops': ['none'], 'splitting_ops': ['vllm::unified_attention', 'vllm::unified_attention_with_output', 'vllm::unified_mla_attention', 'vllm::unified_mla_attention_with_output', 'vllm::mamba_mixer2', 'vllm::mamba_mixer', 'vllm::short_conv', 'vllm::linear_attention', 'vllm::plamo2_mamba_mixer', 'vllm::gdn_attention_core', 'vllm::kda_attention', 'vllm::sparse_attn_indexer', 'vllm::rocm_aiter_sparse_attn_indexer', 'vllm::unified_kv_cache_update'], 'compile_mm_encoder': False, 'compile_sizes': [], 'compile_ranges_split_points': [2048], 'inductor_compile_config': {'enable_auto_functionalized_v2': False, 'combo_kernels': True, 'benchmark_combo_kernel': True}, 'inductor_passes': {}, 'cudagraph_mode': <CUDAGraphMode.FULL_DECODE_ONLY: (2, 0)>, 'cudagraph_num_of_warmups': 1, 'cudagraph_capture_sizes': [1, 2, 4, 8, 16, 24, 32, 40, 48, 56, 64, 72, 80, 88, 96, 104, 112, 120, 128, 136, 144, 152, 160, 168, 176, 184, 192, 200, 208, 216, 224, 232, 240, 248, 256, 272, 288, 304, 320, 336, 352, 368, 384, 400, 416, 432, 448, 464, 480, 496, 512], 'cudagraph_copy_inputs': False, 'cudagraph_specialize_lora': True, 'use_inductor_graph_partition': False, 'pass_config': {'fuse_norm_quant': False, 'fuse_act_quant': False, 'fuse_attn_quant': False, 'eliminate_noops': True, 'enable_sp': False, 'fuse_gemm_comms': False, 'fuse_allreduce_rms': False}, 'max_cudagraph_capture_size': 512, 'dynamic_shapes_config': {'type': <DynamicShapesType.BACKED: 'backed'>, 'evaluate_guards': False, 'assume_32_bit_indexing': True}, 'local_cache_dir': None, 'static_all_moe_layers': []}
(EngineCore_DP0 pid=12321) INFO 02-12 19:34:56 [parallel_state.py:1212] world_size=1 rank=0 local_rank=0 distributed_init_method=tcp://172.29.9.184:48511 backend=nccl
(EngineCore_DP0 pid=12321) INFO 02-12 19:34:56 [parallel_state.py:1423] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, PCP rank 0, TP rank 0, EP rank N/A
(EngineCore_DP0 pid=12321) WARNING 02-12 19:34:56 [interface.py:470] Using 'pin_memory=False' as WSL is detected. This may slow down the performance.
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:05 [gpu_model_runner.py:4033] Starting to load model openai/whisper-large-v3...
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:05 [mm_encoder_attention.py:77] Using AttentionBackendEnum.FLASH_ATTN for MMEncoderAttention.
(EngineCore_DP0 pid=12321) /mnt/c/src/github/wirus_bb_main/vllmWhisper/.venv/lib/python3.12/site-packages/tvm_ffi/_optional_torch_c_dlpack.py:174: UserWarning: Failed to JIT torch c dlpack extension, EnvTensorAllocator will not be enabled.
(EngineCore_DP0 pid=12321) We recommend installing via `pip install torch-c-dlpack-ext`
(EngineCore_DP0 pid=12321)   warnings.warn(
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:29 [cuda.py:364] Using FLASH_ATTN attention backend out of potential backends: ('FLASH_ATTN', 'FLASHINFER', 'TRITON_ATTN', 'FLEX_ATTENTION')
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:29 [cuda.py:364] Using FLASH_ATTN attention backend out of potential backends: ('FLASH_ATTN', 'TRITON_ATTN')
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:30 [weight_utils.py:567] No model.safetensors.index.json found in remote.
Loading safetensors checkpoint shards:   0% Completed | 0/3 [00:00?, ?it/s]
Loading safetensors checkpoint shards:  33% Completed | 1/3 [00:00<00:01,  1.20it/s]
Loading safetensors checkpoint shards:  67% Completed | 2/3 [00:01<00:00,  1.12it/s]
Loading safetensors checkpoint shards: 100% Completed | 3/3 [00:02<00:00,  1.19it/s]
Loading safetensors checkpoint shards: 100% Completed | 3/3 [00:02<00:00,  1.18it/s]
(EngineCore_DP0 pid=12321) 
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:33 [default_loader.py:291] Loading weights took 2.70 seconds
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:33 [gpu_model_runner.py:4130] Model loading took 2.88 GiB memory and 27.944203 seconds
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:34 [gpu_model_runner.py:4958] Encoder cache will be initialized with a budget of 2048 tokens, and profiled with 1 audio items of the maximum feature size.
(EngineCore_DP0 pid=12321) WARNING 02-12 19:35:34 [context.py:472] WhisperProcessor did not return `BatchFeature`. Make sure to match the behaviour of `ProcessorMixin` when implementing custom processors.
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:51 [backends.py:812] Using cache directory: /home/rechenknecht/.cache/vllm/torch_compile_cache/6715ce382d/rank_0_0/backbone for vLLM's torch.compile
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:51 [backends.py:872] Dynamo bytecode transform time: 16.41 s
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:56 [backends.py:267] Directly load the compiled graph(s) for compile range (1, 2048) from the cache, took 2.089 s
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:56 [monitor.py:34] torch.compile takes 18.50 s in total
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:57 [gpu_worker.py:356] Available KV cache memory: 10.14 GiB
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:57 [kv_cache_utils.py:1307] GPU KV cache size: 33,216 tokens
(EngineCore_DP0 pid=12321) INFO 02-12 19:35:57 [kv_cache_utils.py:1312] Maximum concurrency for 448 tokens per request: 26.62x
Capturing CUDA graphs (decode, FULL): 100%|██████████████████████████████████████████| 35/35 [00:02<00:00, 13.85it/s]
(EngineCore_DP0 pid=12321) INFO 02-12 19:36:00 [gpu_model_runner.py:5063] Graph capturing finished in 3 secs, took 0.22 GiB
(EngineCore_DP0 pid=12321) INFO 02-12 19:36:00 [core.py:272] init engine (profile, create kv cache, warmup model) took 26.28 seconds
(EngineCore_DP0 pid=12321) INFO 02-12 19:36:00 [vllm.py:624] Asynchronous scheduling is enabled.
(EngineCore_DP0 pid=12321) WARNING 02-12 19:36:00 [vllm.py:905] No piecewise cudagraph for executing cascade attention. Will fall back to eager execution if a batch runs into cascade attentions.
(APIServer pid=11980) INFO 02-12 19:36:01 [api_server.py:665] Supported tasks: ['transcription']
(APIServer pid=11980) INFO 02-12 19:36:04 [speech_to_text.py:142] Warming up audio preprocessing libraries...
(APIServer pid=11980) INFO 02-12 19:36:30 [speech_to_text.py:178] Audio preprocessing warmup completed in 26.92s
(APIServer pid=11980) INFO 02-12 19:36:30 [speech_to_text.py:205] Warming up multimodal input processor...
(APIServer pid=11980) INFO 02-12 19:36:35 [speech_to_text.py:238] Input processor warmup completed in 4.75s
(APIServer pid=11980) INFO 02-12 19:36:36 [speech_to_text.py:142] Warming up audio preprocessing libraries...
(APIServer pid=11980) INFO 02-12 19:36:36 [speech_to_text.py:178] Audio preprocessing warmup completed in 0.00s
(APIServer pid=11980) INFO 02-12 19:36:36 [speech_to_text.py:205] Warming up multimodal input processor...
(APIServer pid=11980) WARNING 02-12 19:36:36 [context.py:472] WhisperProcessor did not return `BatchFeature`. Make sure to match the behaviour of `ProcessorMixin` when implementing custom processors.
(APIServer pid=11980) INFO 02-12 19:36:36 [speech_to_text.py:238] Input processor warmup completed in 0.00s
(APIServer pid=11980) INFO 02-12 19:36:36 [api_server.py:946] Starting vLLM API server 0 on http://0.0.0.0:8000
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:38] Available routes are:
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /openapi.json, Methods: HEAD, GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /docs, Methods: HEAD, GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /docs/oauth2-redirect, Methods: HEAD, GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /redoc, Methods: HEAD, GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /scale_elastic_ep, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /is_scaling_elastic_ep, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /tokenize, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /detokenize, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /inference/v1/generate, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /pause, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /resume, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /is_paused, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /metrics, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /health, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/chat/completions, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/chat/completions/render, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/responses, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/responses/{response_id}, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/responses/{response_id}/cancel, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/audio/transcriptions, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/audio/translations, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/completions, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/completions/render, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/messages, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/models, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /load, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /version, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /ping, Methods: GET
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /ping, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /invocations, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /classify, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/embeddings, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /score, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/score, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /rerank, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v1/rerank, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /v2/rerank, Methods: POST
(APIServer pid=11980) INFO 02-12 19:36:36 [launcher.py:46] Route: /pooling, Methods: POST
(APIServer pid=11980) INFO:     Started server process [11980]
(APIServer pid=11980) INFO:     Waiting for application startup.
(APIServer pid=11980) INFO:     Application startup complete.

## Client 


curl -s http://localhost:8000/v1/audio/transcriptions \
  -F "model=openai/whisper-large-v3" \
  -F "file=@/path/to/audio.wav" \
  -F "language=en" \
  -F "response_format=verbose_json"


curl -s http://rechenknecht:8000/v1/audio/transcriptions \
  -F "model=openai/whisper-medium" \
  -F "file=file_8---ff54563f-5bc5-4e08-bd4c-487c0f058fc6.ogg" \
  -F "language=de" \
  -F "response_format=verbose_json"

  

# vllm

  

curl -LsSf https://astral.sh/uv/install.sh | sh

source $HOME/.cargo/env

  

sudo apt install python3 python3-pip

uv venv --python 3.12 --seed

source .venv/bin/activate

  

uv pip install "vllm[audio]" --torch-backend=auto

  

# Start Server

  

vllm serve openai/whisper-large-v3 --host 0.0.0.0 --port 8000 --gpu-memory-utilization 0.85

  

# Access from Local Network (WSL)

  

# 1. Get Windows host IP

ipconfig.exe | grep "IPv4" | head -1

  

# 2. Allow port 8000 in Windows Firewall (run in PowerShell as Administrator)

# New-NetFirewallRule -DisplayName "VLLM Server" -Direction Inbound -LocalPort 8000 -Protocol TCP -Action Allow

  



  

# Test Transcription

  

# Convert audio if needed (WebM/Opus to WAV)

sudo apt install ffmpeg

ffmpeg -i input.webm -ar 16000 -ac 1 output.wav -y

  

curl -s http://localhost:8000/v1/audio/transcriptions \

  -F "model=openai/whisper-large-v3" \

  -F "file=@/path/to/audio.wav" \

  -F "language=en" \

  -F "response_format=verbose_json"

  
source .venv/bin/activate && vllm serve openai/whisper-medium --host 0.0.0.0 --port 8000 --gpu-memory-utilization 0.85

___
vllm serve openai/whisper-medium --host 0.0.0.0 --port 8000

| Flag                        | Wirkung                       |
| --------------------------- | ----------------------------- |
| `--uvicorn-log-level debug` | HTTP-Layer Debug              |
| `--enable-log-requests`     | Loggt eingehende API Requests |
| `--enable-log-outputs`      | Loggt Modellantworten         |
| Option                      | Wirkung                       |
| `--uvicorn-log-level debug` | Zeigt HTTP Access Logs        |
| `--enable-log-requests`     | Loggt eingehende API Requests |
| `--disable-log-stats`       | Deaktiviert Performance-Stats |
```
source .venv/bin/activate && vllm serve openai/whisper-medium --host 0.0.0.0 --port 8000 --gpu-memory-utilization 0.85 --uvicorn-log-level debug --enable-log-requests
```
# Links

  
  

https://developers.openai.com/cookbook/articles/gpt-oss/run-vllm/?utm_source=chatgpt.com

https://docs.vllm.ai/en/latest/serving/openai_compatible_server/
