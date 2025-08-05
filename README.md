# SDIK
## 1. SDIK installation

### 1.1 Setup Conda

```
# Conda installation

# For Linux
curl -o ~/miniconda.sh -O https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh

chmod +x ~/miniconda.sh    
./miniconda.sh  

source ~/.bashrc          # For Linux
```

## 1.2 Setup Python environment for GPU

DGL 0.9.1.post1 requires CUDA **11.6**.

For Ubuntu **22.04**
```
# Setup CUDA 11.6 on Ubuntu 22.04
The PyTorch version used in this project is 1.13.1, which corresponds to CUDA 11.6. For compatibility with other CUDA versions, please refer to the official documentation: https://pytorch.org/get-started/previous-versions/

# Install python environment
conda env create -f SDIK.yml

# Activate environment
conda activate SDIK
```
<br><br>
## 2. Download datasets

All the datasets work with DGL 0.5 or later.

### 2.1 TU datasets

Nothing to do. The TU datasets are automatically downloaded.
<br><br>

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
<br><br>
## 4. Add Subgraph counting
To incorporate subgraph counting, please follow the approach provided in https://github.com/magic62442/subgraph-counting to generate subgraph counts for each node. The resulting subgraph count file for each dataset is formatted as a 2D table with dimensions (total number of nodes across all graphs in the dataset, number of k-node graphlet types).


