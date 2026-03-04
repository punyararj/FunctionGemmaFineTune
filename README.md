# 🇹🇭 Fine-tune FunctionGemma-270m-it for Thai Tool Calling

This notebook demonstrates how to:
1. Load **three tool-calling datasets**:
   - `Canfield/tool-calls-dataset` (1,000 examples)
   - `google/mobile-actions` (9,654 examples)
   - `acon96/Home-Assistant-Requests-V2` (~5,000 sampled — smart home control)
2. **Generate Thai general conversations** via Gemma 3 (with tool lists — teaches when NOT to call tools)
3. **Generate tool-rejection examples** (teaches the model to refuse when the needed tool isn't available)
4. Translate user prompts to Thai using `gemma-3-27b-it` on LM Studio
5. Format data in **Gemma 3 chat template** with FunctionGemma's native call format
6. Fine-tune `google/functiongemma-270m-it` using LoRA + SFTTrainer
7. Merge adapter, convert to **GGUF**, and deploy on **Raspberry Pi 5** with **Ollama**
8. Upload model to huggingface hub

---

**Target deployment**: Raspberry Pi 5 → Ollama → GGUF (Q4_K_M quantization)

**Supported platforms**: ✅ NVIDIA CUDA (RTX 3090, etc.) · ✅ Apple Silicon (M1–M4) via MPS · ✅ CPU
