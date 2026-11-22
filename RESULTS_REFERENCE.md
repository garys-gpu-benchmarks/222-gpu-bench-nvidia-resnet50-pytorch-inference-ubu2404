# Results: 222 ResNet-50 BF16 Inference Throughput Sweep

**Main goal:** Measure ResNet-50 BF16 inference throughput  
**Tools:** Run torchvision ResNet-50 eval on synthetic tensors while sampling GPU utilization during the timed loop

Reference results from the validation run on the system shown in each section (recorded 2026-11-22). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 80GB HBM3 (81559 MiB) · Intel(R) Xeon(R) Platinum 8470 · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 595.112.07
- **Run:** 2026-11-22T11:11:58Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:51 · benchmark 00:02 · whole run 02:03
- **Source:** run 222_20261122_111158
- **Command:** `bash run_benchmark.sh --smoke --device-id 0 --dtype bf16 --image-size 64 --batch-size 1,2 --warmup-iters 1 --num-iterations 3 --use-channels-last true`

| # | Metric | Result |
|---|---|---|
| 1 | Largest-batch inference throughput, images/s (images_per_sec) | 698.673124 |
| 2 | Largest-batch per-image latency, ms (per_image_latency_msec) | 1.431284 |
| 3 | Largest-batch latency max, ms (batch_latency_max_msec) | 3.487456 |
| 4 | Largest-batch GPU utilization (gpu_utilization_percent) | 41.2 |
| 5 | Peak GPU memory at largest batch, GB (peak_gpu_memory_gb) | 0.092193 |
<!-- /profile:smoke -->
