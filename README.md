# MedGemma 1.5 4B — 4-bit NF4 Quantized

Quantization, benchmarking, and LiteRT conversion pipeline for `google/medgemma-1.5-4b-it`.

## What This Repo Contains

| File | Description |
|------|-------------|
| `medgemma_quantize_and_convert.ipynb` | Full Colab notebook |

## Pipeline Overview

1. Environment setup & HF authentication
2. Load base FP16 model → generate responses
3. Load 4-bit NF4 quantized model → generate responses
4. Side-by-side benchmark comparison
5. Save quantized model
6. LiteRT conversion for mobile

## Quick Start

1. Open the notebook in Google Colab
2. Accept MedGemma terms at [google/medgemma-1.5-4b-it](https://huggingface.co/google/medgemma-1.5-4b-it)
3. Add your HF token in Colab Secrets as `HF_TOKEN`
4. Run all cells

**Recommended GPU:** L4 (24GB) or A100

## Requirements

```bash
pip install transformers>=4.50.0 accelerate bitsandbytes peft==0.13.2 pillow<11.0.0 huggingface_hub
```

## Benchmark Results

| Metric | FP16 Base | INT4 Quantized |
|--------|-----------|----------------|
| VRAM Usage | ~8 GB | ~3 GB |
| Load Time | Slower | Faster |
| Output Quality | Baseline | Near-identical |

## Quantized Model on Hugging Face

👉 [YOUR_HF_USERNAME/medgemma-1.5-4b-int4](https://huggingface.co/YOUR_HF_USERNAME/medgemma-1.5-4b-int4)

## Important Notice

> ⚠️ For **research purposes only**. Not for clinical or medical decision-making.

## License

Apache 2.0 — Google MedGemma terms also apply.
