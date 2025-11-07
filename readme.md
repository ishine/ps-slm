# PS-SLM

<details>
<summary>📖 English Version</summary>

## Overview

**PS-SLM** (*Phone-Synchronized Speech Language Model*) proposes a novel alignment strategy based on **phone-synchronized decoding**, further improving prior methods such as **LegoSLM** and **SLAM-LLM**. It enhances speech-text alignment quality and strengthens the integration between the encoder and language model components. 

This repository contains two main components:

---

## 📌 1. SLAM-LLM-ASR

An instruction-following **Speech Large Language Model (Speech LLM)** built on the SLAM-LLM-ASR framework. It integrates the **Whisper encoder** or **SenseVoice encoder** into a modular architecture enhanced by **phone-synchronized alignment**, enabling improved transcription accuracy and contextual understanding.

As a condensed and user-friendly version of SLAM-LLM, this component is designed for rapid prototyping of custom Speech LLM architectures.

---

## 📌 2. Whisper-CTC

A standalone CTC training module for fine-tuning the Whisper encoder with support for both standard and **phone-synchronized alignment** strategies.

### Key Features:
- Encoder + CTC training pipeline.
- Support for vocabularies including `sentence_piece`, `gemma-2b`, `qwen-2.5`, and self-defined token sets.
- Flexible freezing/unfreezing of the Whisper encoder.
- Seamless integration with downstream SLAM-style tasks.

> ⚠️ **Notes:**
> - Deepspeed-based distributed training is **not yet supported** — avoid using `train_deepspeed.*` scripts.  
> - The **SLAM-LLM-NPU** environment is **fully supported and verified**.

## Environments:

PS-SLM shares (almost) the same **dependency stack** as  
[SLAM-LLM](https://github.com/X-LANCE/SLAM-LLM), and is further **adapted to Ascend NPUs**.

- Please follow **SLAM-LLM** to install the common dependencies:
- On top of that, configure the **Ascend NPU driver and runtime stack**
  (e.g., CANN, `torch-npu`, etc.) according to your hardware / cluster setup.
- For quickly set up, we will release a tar of dockerfile which could be directly run on 910b.
> ⚠️** Note: **
> - PS-SLM now currently only supports Ascend NPUs.
> - If GPU training is required, simply replace all .npu with .cuda in the code.
> - NVIDIA / CUDA GPU support is coming soon for convenience.

</details>
