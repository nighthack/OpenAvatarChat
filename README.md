<h1 style='text-align: center; margin-bottom: 1rem'>Open Avatar Chat</h1>

<p align="center">
<strong>English</strong>
</p>

<p align="center">
<strong>A modular interactive digital-human chat implementation that can run full functionality on a single PC.</strong>
</p>

<p align="center" style="display: flex; flex-direction: row; justify-content: center">
🤗 <a href="https://huggingface.co/spaces/vishrutJ/open-avatar-chat">Demo on Hugging Face</a>&nbsp;&nbsp;|&nbsp;&nbsp;</a>
</p>

## 🔥 Key Features

* **Low-latency real-time digital-human chat: average response latency around 2.2 seconds.**
* **Multimodal language model support: text, audio, video, etc.**
* **Modular design: flexible component replacement for different feature combinations.**

## 📢 What's New

### Changelog

* **\[2025-06-12] ⭐️⭐️⭐️ Version 0.4.1 released:**

  * Added support for [MuseTalk](https://github.com/TMElyralab/MuseTalk) digital humans with customizable avatars (custom base videos).
  * Released 50 new LiteAvatar models; see [LiteAvatarGallery](https://modelscope.cn/models/HumanAIGC-Engineering/LiteAvatarGallery).
* **\[2025-04-18] ⭐️⭐️⭐️ Version 0.3.0 released:**

  * 🎉 Congratulations on the acceptance of the [LAM](https://github.com/aigc3d/LAM) paper at SIGGRAPH 2025! 🎉
  * Added support for [LAM](https://github.com/aigc3d/LAM) digital humans (single-image, second-level generation of ultra-realistic 3D avatars).
  * Added Builian API TTS handler to greatly reduce GPU dependency.
  * Added Microsoft Edge TTS support.
  * Switched to `uv` for Python package management; install dependencies per activated handler.
  * Updated CSS responsive layout.
* **\[2025-04-14] ⭐️⭐️⭐️ Version 0.2.2 released:**

  * Released 100 new LiteAvatar models; see [LiteAvatarGallery](https://modelscope.cn/models/HumanAIGC-Engineering/LiteAvatarGallery).
  * Default GPU backend for `lite-avatar` digital humans.
* **\[2025-04-07] ⭐️⭐️⭐️ Version 0.2.1 released:**

  * Added history support.
  * Added text input support.
  * No longer requires a camera at startup.
  * Optimized modular loading.
* **\[2025-02-20] ⭐️⭐️⭐️ Version 0.1.0 released:**

  * Modular real-time interactive digital humans.
  * Support for MiniCPM-o as a multimodal language model, or cloud-based API for ASR + LLM + TTS.

### To-do List

* [x] Reach 100 preconfigured digital-human models.
* [x] Integrate [LAM](https://github.com/aigc3d/LAM).
* [ ] Integrate [Qwen2.5-Omni](https://github.com/QwenLM/Qwen2.5-Omni).

## Demo

### Online Demo

We have deployed demo services on:

* <a href="https://www.modelscope.cn/studios/HumanAIGC-Engineering/open-avatar-chat" target="_blank"><img alt="ModelScope" style="height: 10px; margin-right: 1px;" src="./assets/images/modelscope_logo.png"> ModelScope</a>
* <a href="https://huggingface.co/spaces/HumanAIGC-Engineering-Team/open-avatar-chat" target="_blank">🤗 Hugging Face</a>

Audio is powered by `SenseVoice + Qwen-VL + CosyVoice`, with switchable support for `LiteAvatar` and `LAM` digital humans. Feel free to try it out!

### Video Showcase

<table>
  <tr>
    <td align="center">
      <h3>LiteAvatar</h3>
      <video controls src="https://github.com/user-attachments/assets/e2861200-84b0-4c7a-93f0-f46268a0878b"></video>
    </td>
    <td align="center">
      <h3>LAM</h3>
      <video controls src="https://github.com/user-attachments/assets/a72a8c33-39dd-4656-a4a9-b76c5487c711"></video>
    </td>
  </tr>
</table>

## Community

* **WeChat Group**

<img alt="WeChat QR Code" src="https://github.com/HumanAIGC-Engineering/OpenAvatarChat/blob/main/assets/images/community_wechat.png" width="200" height="200"/>

## 🚨 FAQ

Common issues encountered during development can be found in the [FAQ](./docs/FAQ.md).

## 📖 Table of Contents

* [🔥 Key Features](#-key-features)
* [📢 What's New](#-whats-new)

  * [Changelog](#changelog)
  * [To-do List](#to-do-list)
* [Demo](#demo)

  * [Online Demo](#online-demo)
  * [Video Showcase](#video-showcase)
* [Community](#community)
* [🚨 FAQ](#-faq)
* [Overview](#overview)

  * [Introduction](#introduction)
  * [System Requirements](#system-requirements)
  * [Performance Metrics](#performance-metrics)
  * [Component Dependencies](#component-dependencies)
  * [Preset Modes](#preset-modes)
* [🚀 Installation & Deployment](#-installation--deployment)

  * [Choosing a Configuration](#choosing-a-configuration)

    * [chat\_with\_gs.yaml](#chat_with_gsyaml)

      * [Handlers Used](#handlers-used)
    * [chat\_with\_minicpm.yaml](#chat_with_minicpmyaml)

      * [Handlers Used](#handlers-used-1)
    * [chat\_with\_openai\_compatible.yaml](#chat_with_openai_compatibleyaml)

      * [Handlers Used](#handlers-used-2)
    * [chat\_with\_openai\_compatible\_edge\_tts.yaml](#chat_with_openai_compatible_edge_ttsyaml)

      * [Handlers Used](#handlers-used-3)
    * [chat\_with\_openai\_compatible\_bailian\_cosyvoice.yaml](#chat_with_openai_compatible_bailian_cosyvoiceyaml)

      * [Handlers Used](#handlers-used-4)
    * [chat\_with\_openai\_compatible\_bailian\_cosyvoice\_musetalk.yaml](#chat_with_openai_compatible_bailian_cosyvoice_musetalkyaml)

      * [Handlers Used](#handlers-used-5)
  * [Local Run](#local-run)

    * [uv Installation](#uv-installation)
    * [Dependency Installation](#dependency-installation)

      * [Install All Dependencies](#install-all-dependencies)
      * [Install Only Required Dependencies](#install-only-required-dependencies)
    * [Run](#run)
  * [Docker Run](#docker-run)
* [Handler Dependency Guides](#handler-dependency-guides)

  * [RTC Client Handler (Server-side Rendering)](#rtc-client-handler-server-side-rendering)
  * [LAM Client Handler (Edge Rendering)](#lam-client-handler-edge-rendering)
  * [OpenAI-Compatible Language Model Handler](#openai-compatible-language-model-handler)
  * [MiniCPM Multimodal Language Model Handler](#minicpm-multimodal-language-model-handler)
  * [Bailian CosyVoice TTS Handler](#bailian-cosyvoice-tts-handler)
  * [CosyVoice Local Inference Handler](#cosyvoice-local-inference-handler)
  * [Edge TTS Handler](#edge-tts-handler)
  * [LiteAvatar Handler](#liteavatar-handler)
  * [LAM Audio2Expression Handler](#lam-audio2expression-handler)
  * [MuseTalk Handler](#musetalk-handler)
* [Related Deployment Requirements](#related-deployment-requirements)

  * [SSL Certificates](#ssl-certificates)
  * [TURN Server](#turn-server)
  * [Configuration Guide](#configuration-guide)
* [Acknowledgements](#acknowledgements)
* [Star History](#star-history)
* [Citation](#citation)

## Overview

### Introduction

Open Avatar Chat is a modular interactive digital-human chat implementation that can run full functionality on a single PC. It currently supports MiniCPM-o as a multimodal language model, or can use cloud-based APIs to replace ASR + LLM + TTS. The architectures for both modes are shown below. More preset modes are listed in [Preset Modes](#preset-modes).

<p align="center">
<img src="./assets/images/data_flow.svg" alt="Data Flow" />
</p>

### System Requirements

* Python ≥ 3.11.7, < 3.12
* CUDA-capable GPU
* Unquantized MiniCPM-o requires ≥ 20GB VRAM
* Digital-human rendering can use GPU/CPU (tested on i9-13980HX CPU achieving 30 FPS)

> **Tip:** An int4-quantized LM can run on <10GB VRAM with reduced performance. Using cloud-based APIs for ASR + LLM + TTS greatly lowers hardware requirements; see [ASR + LLM + TTS mode](#chat_with_openai_compatible_bailian_cosyvoiceyaml).

### Performance Metrics

On a PC with an i9-13900KF and an NVIDIA RTX 4090, we measured response latency over ten runs: average \~2.2s. Latency is measured from end of user speech to start of avatar speech, including RTC round-trip, VAD end delay, and computation time.

### Component Dependencies

| Type     | Open Source Project                 | GitHub Link                                                      | Model Link                                                                                                              |
| -------- | ----------------------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| RTC      | HumanAIGC-Engineering/gradio-webrtc | [GitHub](https://github.com/HumanAIGC-Engineering/gradio-webrtc) |                                                                                                                         |
| VAD      | snakers4/silero-vad                 | [GitHub](https://github.com/snakers4/silero-vad)                 |                                                                                                                         |
| LLM      | OpenBMB/MiniCPM-o                   | [GitHub](https://github.com/OpenBMB/MiniCPM-o)                   | [🤗](https://huggingface.co/openbmb/MiniCPM-o-2_6), <img src="./assets/images/modelscope_logo.png" width="20px"/>       |
| LLM-int4 | OpenBMB/MiniCPM-o                   | [GitHub](https://github.com/OpenBMB/MiniCPM-o)                   | [🤗](https://huggingface.co/openbmb/MiniCPM-o-2_6-int4), <img src="./assets/images/modelscope_logo.png" width="20px"/>  |
| Avatar   | HumanAIGC/lite-avatar               | [GitHub](https://github.com/HumanAIGC/lite-avatar)               |                                                                                                                         |
| TTS      | FunAudioLLM/CosyVoice               | [GitHub](https://github.com/FunAudioLLM/CosyVoice)               |                                                                                                                         |
| Avatar   | aigc3d/LAM\_Audio2Expression        | [GitHub](https://github.com/aigc3d/LAM_Audio2Expression)         | [🤗](https://huggingface.co/3DAIGC/LAM_audio2exp)                                                                       |
| ASR      | facebook/wav2vec2-base-960h         |                                                                  | [🤗](https://huggingface.co/facebook/wav2vec2-base-960h), <img src="./assets/images/modelscope_logo.png" width="20px"/> |
| Avatar   | TMElyralab/MuseTalk                 | [GitHub](https://github.com/TMElyralab/MuseTalk)                 |                                                                                                                         |

### Preset Modes

| CONFIG Name                                                       | ASR        | LLM       | TTS       | Avatar      |
| ----------------------------------------------------------------- | ---------- | --------- | --------- | ----------- |
| chat\_with\_gs.yaml                                               | SenseVoice | Cloud API | Cloud API | LAM         |
| chat\_with\_minicpm.yaml                                          | MiniCPM-o  | MiniCPM-o | MiniCPM-o | lite-avatar |
| chat\_with\_openai\_compatible.yaml                               | SenseVoice | Cloud API | CosyVoice | lite-avatar |
| chat\_with\_openai\_compatible\_edge\_tts.yaml                    | SenseVoice | Cloud API | edge-tts  | lite-avatar |
| chat\_with\_openai\_compatible\_bailian\_cosyvoice.yaml           | SenseVoice | Cloud API | Cloud API | lite-avatar |
| chat\_with\_openai\_compatible\_bailian\_cosyvoice\_musetalk.yaml | SenseVoice | Cloud API | Cloud API | MuseTalk    |

## 🚀 Installation & Deployment

Refer to each mode's handler installation guide and [related deployment requirements](#related-deployment-requirements) before installation.

### Choosing a Configuration

OpenAvatarChat is launched via a config file in `config/`. Available presets:

#### chat\_with\_gs.yaml

Uses LAM for edge-side rendering and Bailian CosyVoice for TTS, with only VAD & ASR locally on GPU—light hardware footprint

##### Handlers Used

| Category | Handler                                               | Installation Guide                                                        |
| -------- | ----------------------------------------------------- | ------------------------------------------------------------------------- |
| Client   | `client/h5_rendering_client/client_handler_lam`       | [LAM Edge Rendering Client Handler](#lam-client-handler-edge-rendering)   |
| VAD      | `vad/silerovad/vad_handler/silero`                    |                                                                           |
| ASR      | `asr/sensevoice/asr_handler_sensevoice`               |                                                                           |
| LLM      | `llm/openai_compatible/llm_handler_openai_compatible` | [OpenAI-Compatible LM Handler](#openai-compatible-language-model-handler) |
| TTS      | `tts/bailian_tts/tts_handler_cosyvoice_bailian`       | [Bailian CosyVoice Handler](#bailian-cosyvoice-tts-handler)               |
| Avatar   | `avatar/lam/avatar_handler_lam_audio2expression`      | [LAM Audio2Expression Handler](#lam-audio2expression-handler)             |

... and similarly for other config files (see full list above).

### Local Run

> **Important:** This project uses Git submodules and large models via Git LFS. Ensure Git LFS is installed and submodules are updated:
>
> ```bash
> sudo apt install git-lfs
> git lfs install
> git submodule update --init --recursive
> ```
>
> We recommend cloning rather than downloading ZIPs for submodule and LFS support. If issues arise, please file an [issue](https://github.com/HumanAIGC-Engineering/OpenAvatarChat/issues).

#### uv Installation

Install [uv](https://docs.astral.sh/uv/) for environment management:

```bash
# Windows
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh
# Or via pip
pip install uv
# Or via pipx
pipx install uv
```

#### Dependency Installation

##### Install All Dependencies

```bash
uv sync --all-packages
```

##### Install Only Required Dependencies for a Mode

```bash
uv venv --python 3.11.11
uv pip install setuptools pip
uv run install.py --uv --config <absolute-path-to-config>.yaml
./scripts/post_config_install.sh --config <absolute-path-to-config>.yaml
```

> **Note:** `post_config_install.sh` adds NVIDIA CUDA library paths to `ld.so.conf.d` and updates the cache via `ldconfig`.

#### Run

```bash
uv run src/demo.py --config <absolute-path-to-config>.yaml
```

### Docker Run

Containerized deployment (requires NVIDIA Docker support):

```bash
./build_and_run.sh --config <absolute-path-to-config>.yaml
```

## Handler Dependency Guides

### RTC Client Handler (Server-side Rendering)

No special dependencies or setup required.

### LAM Client Handler (Edge Rendering)

Extends the server-side RTC handler for multi-stream support; select avatar via config (see sample config under `scripts/`).

### OpenAI-Compatible Language Model Handler

Use any LLM API key; configure model, system prompt, API URL, and key in config or via env vars.

```yaml
LLM_Bailian:
  model_name: "qwen-plus"
  system_prompt: "You are an AI digital human..."
  api_url: 'https://dashscope.aliyuncs.com/compatible-mode/v1'
  api_key: 'YOUR_API_KEY' # or env var
```

...and so on for each handler (MiniCPM, CosyVoice, Edge TTS, LiteAvatar, LAM Audio2Exp, MuseTalk).

## Related Deployment Requirements

### SSL Certificates

For non-localhost RTC connections, provide `localhost.crt` and `localhost.key` in `ssl_certs/`, or generate via:

```bash
scripts/create_ssl_certs.sh
```

### TURN Server

If clients stall on "waiting for connection", set up a TURN server (e.g., coturn); see `scripts/setup_coturn.sh` and update config under `RtcClient.turn_config`.

### Configuration Guide

By default, `config/chat_with_minicpm.yaml` is used. Override with:

```bash
uv run src/demo.py --config <absolute-path-to-config>.yaml
```

## Acknowledgements

* Thanks to “十字鱼” for the one-click installer video on Bilibili and provided package.
* Thanks to “W\&H” for Quark one-click packages (Windows and Linux).

## Star History

![](https://api.star-history.com/svg?repos=HumanAIGC-Engineering/OpenAvatarChat\&type=Date)

## Citation

If OpenAvatarChat helps in your research or projects, please give us a ⭐ and cite:

```bibtex
@software{avatarchat2025,
  author = {Gang Cheng, Tao Chen, Feng Wang, Binchao Huang, Hui Xu, Guanqiao He, Yi Lu, Shengyin Tan},
  title = {OpenAvatarChat},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/HumanAIGC-Engineering/OpenAvatarChat}
}
```
