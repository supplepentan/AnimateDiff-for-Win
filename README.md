# AnimateDiff for Win

## Introduction

This is Windows model of AnimateDiff.

Original: [AnimateDiff](https://github.com/guoyww/AnimateDiff)

### Dependencies

- OS: Windows
- nvidia:
  - cuda: 11.7
- python 3.10.5 (using Pyenv)

## Install

## Clone from GitHub

Clone from GitHub, and move to the folder " AnimateDiff-for-Win ".

```bash
git clone https://github.com/supplepentan/AnimateDiff-for-Win
cd AnimateDiff-for-Win
```

## Virtual environment

Virtual environment with Python-version 3.10.5 using Pyenv.

```bash
pyenv local 3.10.5
python -m venv venv
venv/scripts/activate
```

## Libraries

Install libraries using " reqruirements.txt "

```bash
python -m pip install -r requirements.txt
```

### Pytorch

Uninstall unnecessary installed Pytorch, and newly install Pytorch (CUDA11.7 compatible model).

```bash
python -m pip install torch==1.13.1 torchvision==0.14.1 --index-url https://download.pytorch.org/whl/cu117
```

### Xformers

Download " [xformers-0.0.14.dev0-cp310-cp310-win_amd64.whl](https://github.com/C43H66N12O12S2/stable-diffusion-webui/releases) " at root, and install.

```bash
python -m pip install xformers-0.0.14.dev0-cp310-cp310-win_amd64.whl
```

## StableDiffusion

```bash
git lfs install
git clone https://huggingface.co/runwayml/stable-diffusion-v1-5 models/StableDiffusion/stable-diffusion-v1-5
```

## Models

### Motion Module

Download and put the models to folder " models/Motion_Module/ ".

[Motion Modules](https://drive.google.com/drive/folders/1EqLC65eR1-W-sGD0Im7fkED6c8GkiNFI)

| Name              | Parameter | Storage Space |
| ----------------- | --------- | ------------- |
| mm_sd_v14.ckpt    | 417 M     | 1.6 GB        |
| mm_sd_v15.ckpt    | 417 M     | 1.6 GB        |
| mm_sd_v15_v2.ckpt | 453 M     | 1.7 GB        |

[MotionLoRAs](https://drive.google.com/drive/folders/1EqLC65eR1-W-sGD0Im7fkED6c8GkiNFI)

| Name                              | Parameter | Storage Space |
| --------------------------------- | --------- | ------------- |
| v2_lora_ZoomIn.ckpt               | 19 M      | 74 MB         |
| v2_lora_ZoomOut.ckpt              | 19 M      | 74 MB         |
| v2_lora_PanLeft.ckpt              | 19 M      | 74 MB         |
| v2_lora_PanRight.ckpt             | 19 M      | 74 MB         |
| v2_lora_TiltUp.ckpt               | 19 M      | 74 MB         |
| v2_lora_TiltDown.ckpt             | 19 M      | 74 MB         |
| v2_lora_RollingClockwise.ckpt     | 19 M      | 74 MB         |
| v2_lora_RollingAnticlockwise.ckpt | 19 M      | 74 MB         |

### DreamBooth LoRA

Download and put the models to folder " models/DreamBooth_LoRA/ ".

[toonyou_beta3.safetensors](https://civitai.com/api/download/models/78775)

[realisticVisionV20_v20.safetensors](https://huggingface.co/ckpt/realistic-vision-v20/blob/main/realisticVisionV20_v20.safetensors)

### Test

```bash
python -m scripts.animate --config configs/prompts/v2/5-RealisticVision-MotionLoRA.yaml
```

## Run the Gradio

```bash
python app.py
```

Access to http://127.0.0.1:7860 .

## Acknowledgements

This code is built on [AnimateDiff](https://github.com/guoyww/AnimateDiff), thank for the authors for sharing their codes.
