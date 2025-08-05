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

## 2. Download datasets

All the datasets work with DGL 0.5 or later.

<br>

### 2.1 TU datasets

Nothing to do. The TU datasets are automatically downloaded.
<br>

## 3. run_codes

### 3.1 In terminal
```
python main_TUs_graph_classification.py --dataset MUTAG --gpu_id 0 --seed 41 --config 'configs/TUs_graph_classification_GAT_MUTAG_100k.json' --subgraph_counting 'data/counting/MUTAG/merge/lz_456node_graphlets' --gridsearch --split_number 0
```
The training and network parameters for each dataset and network is stored in a json file in the [`configs/`](./configs) directory.

### 3.2 Reproduce results
```
bash run_all_SDIK.sh | tee total_output.log
```
