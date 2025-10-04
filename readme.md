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

</details>

---

<details>
<summary>📘 中文版本</summary>

## 项目简介

**PS-SLM**（Phone-Synchronized Speech Language Model）提出了一种基于**音素同步解码（Phone-Synchronized Decoding）**的新型对齐方式，在 **LegoSLM** 与 **SLAM-LLM** 的基础上进一步改进了语音与文本的对齐策略，提升了语音理解的对齐精度，并加强了编码器与语言模型之间的融合效果。

本项目主要包含两个核心模块：

---

## 📌 1. SLAM-LLM-ASR

一个基于 SLAM-LLM-ASR 框架的指令遵循型 **语音大语言模型（Speech LLM）**。该模块集成了 **Whisper 编码器**或 **SenseVoice 编码器**，采用模块化设计，并引入了**音素同步对齐**机制，提升了转录性能和上下文理解能力。

该模块作为 SLAM-LLM 的精简版，具备更强的可用性和扩展性，便于快速搭建自定义的 Speech LLM 架构。

---

## 📌 2. Whisper-CTC

独立的 CTC 训练模块，用于微调 Whisper 编码器，支持传统对齐与**音素同步对齐**两种训练方式。

---

## 📌 3. sense_voice_LLM

使用sensevoice作为encoder的LegoSLM论文基线，CTC后验概率加权嵌入LLM embedding空间

---

### 主要特性：
- 支持 Encoder + CTC 的训练范式；
- 兼容多种词表：`sentence_piece`、`gemma-2b`、`qwen-2.5`、自定义词表等；
- 支持 Whisper 编码器参数的灵活冻结与解冻；
- 可与 SLAM 风格任务无缝集成。

> ⚠️ **注意事项：**  
> - 当前暂不支持基于 Deepspeed 的分布式训练，**请勿使用 `train_deepspeed.*` 系列脚本**；  
> - 已全面适配并验证 **SLAM-LLM-NPU 环境**，可稳定运行。

</details>
