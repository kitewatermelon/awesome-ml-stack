# ⚡ Awesome PyTorch Ecosystem & ML Libraries

> A curated archive of third-party libraries, frameworks, and tools built on or around PyTorch and the modern ML stack.  
> Maintained by [@yeonsupark](https://kitewatermelon.github.io) · Last updated: 2026-03

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

---

## 📌 How to Read This List

Each entry follows this format:

```
**[Library Name](repo-url)** `vX.Y.Z` — Short one-line description.
> 🔧 Backend: PyTorch / JAX / Both  
> 📦 Install: `pip install ...`  
> 📝 Notes: Personal notes, use cases, caveats.  
> 🏷️ Tags: #self-supervised #pretraining #vision
```

---

## 📚 Table of Contents

- [Training Frameworks](#-training-frameworks)
- [Pretraining & Self-Supervised Learning](#-pretraining--self-supervised-learning)
- [World Models & Generative](#-world-models--generative)
- [Distributed Training](#-distributed-training)
- [Vision & ViT Ecosystem](#-vision--vit-ecosystem)
- [Medical Imaging](#-medical-imaging)
- [Neuroimaging & Brain AI](#-neuroimaging--brain-ai)
- [Data Loading & Augmentation](#-data-loading--augmentation)
- [Experiment Tracking & Tooling](#-experiment-tracking--tooling)
- [Imaging Genetics & Multimodal](#-imaging-genetics--multimodal)

---

## 🏗 Training Frameworks

**[PyTorch Lightning](https://github.com/Lightning-AI/pytorch-lightning)** `v2.x` — High-level PyTorch wrapper that removes boilerplate while keeping full flexibility.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install lightning`  
> 📝 Notes: Trainer 추상화가 DDP 세팅을 크게 단순화함. `fabric` 모드가 더 가벼워서 커스텀 루프에 적합.  
> 🏷️ Tags: #framework #ddp #training-loop

---

**[TorchDR](https://github.com/TorchDR/TorchDR)** `v0.x` — GPU-accelerated dimensionality reduction (UMAP, t-SNE, etc.) built natively in PyTorch.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install torchdr`  
> 📝 Notes: 피처 공간 시각화 및 latent space 분석에 유용. sklearn 인터페이스와 호환.  
> 🏷️ Tags: #dimensionality-reduction #visualization #umap #tsne

---

## 🔬 Pretraining & Self-Supervised Learning

**[Stable Pretraining](https://github.com/...)** `v0.x` — Stable, reproducible pretraining recipes for vision/language models.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install stable-pretraining`  
> 📝 Notes: MAE, JEPA류 아키텍처 재현 실험에 활용.  
> 🏷️ Tags: #self-supervised #pretraining #mae #jepa

---

**[VISSL](https://github.com/facebookresearch/vissl)** — Facebook Research의 self-supervised vision 라이브러리. SimCLR, MoCo, BYOL, SwAV 등 표준 구현 포함.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install vissl`  
> 📝 Notes: 논문 재현 레퍼런스로 활용. 현재 유지보수 축소 상태.  
> 🏷️ Tags: #self-supervised #contrastive #vision

---

**[lightly](https://github.com/lightly-ai/lightly)** — Self-supervised learning framework. 최신 SSL 기법 (VICReg, Barlow Twins, SimSiam 등) 간편 사용.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install lightly`  
> 📝 Notes: 커스텀 백본과 조합이 편리. 의료 이미징 사전학습 실험에 적합.  
> 🏷️ Tags: #self-supervised #contrastive #pretraining

---

## 🌍 World Models & Generative

**[Stable World Model](https://github.com/...)** `v0.x` — Latent world model framework for video prediction and planning.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install stable-worldmodel`  
> 📝 Notes: RSSM 계열 구조. Brain dynamics 모델링에 응용 가능성 검토 중.  
> 🏷️ Tags: #world-model #generative #video #latent-space

---

**[diffusers](https://github.com/huggingface/diffusers)** — HuggingFace의 diffusion model 라이브러리. DDPM, LDM, Score Matching 등.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install diffusers`  
> 📝 Notes: CBCT-to-CT synthesis 파이프라인에서 핵심으로 사용. scheduler 커스터마이징이 용이.  
> 🏷️ Tags: #diffusion #generative #image-synthesis

---

## 🔀 Distributed Training

**[torchrun / DDP](https://pytorch.org/docs/stable/distributed.html)** — PyTorch 내장 분산 학습 모듈.
> 🔧 Backend: PyTorch  
> 📝 Notes: 8×A6000 환경에서 `torchrun --nproc_per_node=8` 기본 세팅. `torch.compile`과 조합 시 주의 필요.  
> 🏷️ Tags: #distributed #ddp #multi-gpu

---

**[DeepSpeed](https://github.com/microsoft/DeepSpeed)** — Microsoft의 대규모 모델 학습 최적화 라이브러리.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install deepspeed`  
> 📝 Notes: ZeRO-2/3 옵티마이저 상태 분산으로 메모리 절감. ViT 대형 실험 시 검토.  
> 🏷️ Tags: #distributed #memory-efficient #large-model

---

## 👁 Vision & ViT Ecosystem

**[timm](https://github.com/huggingface/pytorch-image-models)** — 수백 개의 사전학습 vision 모델 허브. ViT, Swin, ConvNeXt 등.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install timm`  
> 📝 Notes: 백본 로드 및 feature extraction의 사실상 표준.  
> 🏷️ Tags: #vision #vit #backbone #pretrained

---

**[einops](https://github.com/arogozhnikov/einops)** — 텐서 연산을 readable하게 표현하는 라이브러리.
> 🔧 Backend: PyTorch / NumPy / JAX  
> 📦 Install: `pip install einops`  
> 📝 Notes: ViT의 patch embedding, attention reshape 코드가 훨씬 명확해짐.  
> 🏷️ Tags: #tensor #utility #vit

---

## 🏥 Medical Imaging

**[MONAI](https://github.com/Project-MONAI/MONAI)** — 의료 영상 딥러닝 전용 프레임워크.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install monai`  
> 📝 Notes: CT/MRI 전처리, augmentation, 3D 모델링 전반. CBCT 파이프라인에 활용.  
> 🏷️ Tags: #medical-imaging #3d #segmentation #ct

---

**[TorchIO](https://github.com/fepegar/torchio)** — MRI/CT용 데이터 augmentation 및 전처리 라이브러리.
> 🔧 Backend: PyTorch  
> 📦 Install: `pip install torchio`  
> 📝 Notes: RandomAffine, RandomGhosting 등 MRI-specific augmentation이 풍부.  
> 🏷️ Tags: #medical-imaging #mri #augmentation

---

## 🧠 Neuroimaging & Brain AI

**[nilearn](https://nilearn.github.io)** — fMRI / sMRI 분석용 Python 라이브러리.
> 🔧 Backend: NumPy / scikit-learn  
> 📦 Install: `pip install nilearn`  
> 📝 Notes: AAL3v2 아틀라스 기반 ROI 추출 및 functional connectivity matrix 계산에 핵심 사용.  
> 🏷️ Tags: #neuroimaging #fmri #connectivity

---

**[niworkflows](https://github.com/nipreps/niworkflows)** — fMRIPrep 기반 워크플로우 컴포넌트.
> 📦 Install: `pip install niworkflows`  
> 📝 Notes: ADNI 데이터 전처리 파이프라인 참고.  
> 🏷️ Tags: #neuroimaging #preprocessing #fmriprep

---

## 📦 Data Loading & Augmentation

**[Albumentations](https://github.com/albumentations-team/albumentations)** — 빠른 이미지 augmentation 라이브러리.
> 📦 Install: `pip install albumentations`  
> 🏷️ Tags: #augmentation #vision #fast

---

**[WebDataset](https://github.com/webdataset/webdataset)** — 대규모 데이터셋을 tar 스트리밍으로 처리.
> 📦 Install: `pip install webdataset`  
> 📝 Notes: 대용량 neuroimaging 데이터셋 로딩 최적화에 검토 예정.  
> 🏷️ Tags: #data-loading #streaming #large-scale

---

## 📊 Experiment Tracking & Tooling

**[Weights & Biases (wandb)](https://wandb.ai)** — 실험 추적, 하이퍼파라미터 스윕, 시각화.
> 📦 Install: `pip install wandb`  
> 📝 Notes: DDP 실험에서 `wandb.init(group=...)` 로 멀티 GPU 로그 통합. sweep 설정으로 배치 사이즈, lr 탐색.  
> 🏷️ Tags: #experiment-tracking #logging #sweep

---

**[uv](https://github.com/astral-sh/uv)** — Rust 기반 초고속 Python 패키지 매니저.
> 📦 Install: `curl -LsSf https://astral.sh/uv/install.sh | sh`  
> 📝 Notes: ijepa 환경 세팅 시 conda 대비 의존성 해결이 빠름. `uv pip install -e .` 패턴 선호.  
> 🏷️ Tags: #tooling #package-manager #python

---

## 🧬 Imaging Genetics & Multimodal

**[statsmodels](https://www.statsmodels.org)** — 통계 모델링 및 회귀 분석.
> 📝 Notes: SCCA 전처리 단계 및 SNP 표현형 연관 분석에 활용.  
> 🏷️ Tags: #statistics #genetics #regression

---

**[PySnpTools](https://github.com/fastlmm/PySnpTools)** — PLINK BED 포맷 SNP 데이터 I/O.
> 📦 Install: `pip install pysnptools`  
> 📝 Notes: GWAS 데이터 로딩 및 imaging genetics 파이프라인 입력단.  
> 🏷️ Tags: #genetics #snp #gwas #imaging-genetics

---

## 🤝 Contributing

항목 추가 시 아래 형식을 지켜주세요:

```
**[Name](url)** `vX.Y` — 한 줄 설명 (영문 또는 한국어).
> 🔧 Backend: ...  
> 📦 Install: `pip install ...`  
> 📝 Notes: ...  
> 🏷️ Tags: #tag1 #tag2
```

- 개인 노트(`📝 Notes`)는 자유롭게 작성
- 태그는 기존 태그 재사용 권장
- 섹션이 맞지 않으면 PR로 새 섹션 제안

---

## 📄 License

[MIT](LICENSE) · Made with ☕ by 박연수
