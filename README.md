# Florence2 + SAM 2: Fire and Smoke Detection in CCTV images and videos

This repository is build up using SAM2 model from Meta AI Research and Florence2 model from Microsoft Research. The main goal of this project is to detect fire and smoke in CCTV images and videos in real time.

| ![](./assets/pipeline_diagram.png)                                                            
|------------------------------------------------------------------------------------------------|
| <p align="center"> <b>Figure 1: Florence2 and SAM2 pipeline for fire and smoke detection</b> . |

## System Requirements
**Hardware Requirments:**
At least 32GB of RAM and 24GB of GPU memory is required to run the model.

**Software Requirments:**
* [Python >= 3.10](https://www.python.org/downloads/)
* [Anaconda](https://docs.anaconda.com/anaconda/install/)
* [CUDA >= 11.7](https://developer.nvidia.com/cuda-11-7-0-download-archive)

## Getting started
```
git clone https://github.com/jaswindersingh2/fire-and-smoke-detectors.git
cd fire-and-smoke-detectors
```

### Create Conda Virtual Environment and Install Dependencies

Create virtual environment
```
conda create -n venv python=3.10 anaconda
```

Activate the conda environment
```
conda activate venv
```

Install PyTorch
```
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

Install SAM2 dependencies
```
pip install -e .
```

Install florence2 dependencies
```
pip install -q transformers flash_attn timm einops supervision==0.22.0rc1
```

### Download Checkpoints

To SAM2.1 checkpoints

```bash
cd checkpoints && \
./download_ckpts.sh && \
cd ..
```

### Run Inference notebook

Local computer running the notebook:

```
jupyter notebook
```

Server computer running the notebook:

```
jupyter notebook --no-browser --ip=0.0.0.0
```

Then open the notebook [inference.ipynb](inference.ipynb) and run the cells to get florence2 + SAM2 pipeline output.