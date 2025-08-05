# test
## 1. SDIK installation
<br>

### 1.1 Setup Conda

```
# Conda installation

# For Linux
curl -o ~/miniconda.sh -O https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh

chmod +x ~/miniconda.sh    
./miniconda.sh  

source ~/.bashrc          # For Linux
```
<br>

## 1.2 Setup Python environment for GPU

DGL 0.9.1.post1 requires CUDA **11.6**.

For Ubuntu **22.04**
```
# Setup CUDA 11.6 on Ubuntu 22.04

# Install python environment
conda env create -f SDIK.yml

# Activate environment
conda activate SDIK
```
<br><br>
