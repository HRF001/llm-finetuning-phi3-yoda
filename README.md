# llm-finetuning-phi3-yoda

Fine-tuning Microsoft's Phi-3-mini to speak in Yoda style using LoRA (Low-Rank Adaptation).

## 🎯 Project Overview

This project fine-tunes the `microsoft/Phi-3-mini-4k-instruct` model on a small dataset of Yoda-style sentences, teaching it to respond with the iconic inverted syntax of the Star Wars character. The goal is to demonstrate the workflow of parameter-efficient fine-tuning (PEFT) on a modern small language model using consumer-grade hardware (Google Colab T4 GPU).

## ✨ Results

**Prompt:** `The Force is strong in you!`  
**Model output:** `Strong in you, the Force is! Yes, hrrrm.`

**Prompt:** `What should I do when I feel sad?`  
**Model output:** `When you feel sad, what should you do? Hmm.`

The model successfully learned the inverted sentence structure characteristic of Yoda's speech.

## 🛠️ Tech Stack

- **Base model:** Microsoft Phi-3-mini-4k-instruct (3.8B parameters)
- **Fine-tuning method:** LoRA via the `peft` library
- **Quantization:** 4-bit (QLoRA) using `bitsandbytes`
- **Training framework:** `transformers` + `trl` (SFTTrainer)
- **Dataset:** `dvgodoy/yoda_sentences` (720 English-to-Yoda sentence pairs)
- **Hardware:** Google Colab (NVIDIA T4 GPU, 16GB)

## 📁 Repository Structure

- `Fine_Tuning_Your_First_Large_Language_Model.ipynb` — Main training notebook
- `README.md` — This file
- `LICENSE` — MIT License
- `.gitignore` — Python gitignore

## 🚀 How to Reproduce

1. Open the notebook in [Google Colab](https://colab.research.google.com/).
2. Set the runtime to **GPU (T4)**: `Runtime` → `Change runtime type` → `T4 GPU`.
3. Run all cells. Training takes approximately 1-2 hours on a free Colab T4.
4. The fine-tuned LoRA adapter will be saved locally and can optionally be pushed to the Hugging Face Hub.

## 📚 What I Learned

- The end-to-end workflow of fine-tuning an LLM: dataset preparation, tokenization, LoRA configuration, training with `SFTTrainer`, and inference.
- How LoRA dramatically reduces trainable parameters (typically <1% of the base model) while maintaining strong task performance.
- Practical use of 4-bit quantization to fit billion-parameter models on consumer GPUs.
- The importance of prompt templates in instruction-tuned models.

## 🔮 Next Steps

- Experiment with larger datasets and different training hyperparameters.
- Try fine-tuning on a different stylistic task (e.g., Shakespeare-style English).
- Move on to a domain-specific fine-tuning project (e.g., medical Q&A or code generation).

## 📖 References

- [Fine-Tuning Your First Large Language Model with PyTorch and Hugging Face](https://huggingface.co/blog/dvgodoy/fine-tuning-llm-hugging-face) — the tutorial this project is based on.
- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685)
- [Hugging Face PEFT documentation](https://huggingface.co/docs/peft)

## 📄 License

MIT License — see [LICENSE](LICENSE) file for details.
