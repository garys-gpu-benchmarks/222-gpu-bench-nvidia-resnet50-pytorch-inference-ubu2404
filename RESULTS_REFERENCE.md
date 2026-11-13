# Results: 222 ResNet-50 BF16 Inference Throughput Sweep

**Main goal:** Measure ResNet-50 BF16 inference throughput  
**Tools:** Run torchvision ResNet-50 eval on synthetic tensors while sampling GPU utilization during the timed loop

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_138 · recorded 2026-11-12). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-12T23:15:13Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:15 · benchmark 00:08 · whole run 01:37
- **Source:** run 222_20261112_231513
- **Command:** `bash run_benchmark.sh --smoke --device-id 0 --dtype bf16 --image-size 64 --batch-size 1,2 --warmup-iters 1 --num-iterations 3 --use-channels-last true`

| # | Metric | Result |
|---|---|---|
| 1 | Largest-batch inference throughput, images/s (images_per_sec) | 575.008052 |
| 2 | Largest-batch per-image latency, ms (per_image_latency_msec) | 1.739106 |
| 3 | Largest-batch latency max, ms (batch_latency_max_msec) | 4.103104 |
| 4 | Largest-batch GPU utilization (gpu_utilization_percent) | 18.5 |
| 5 | Peak GPU memory at largest batch, GB (peak_gpu_memory_gb) | 0.092193 |
<!-- /profile:smoke -->
