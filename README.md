# Spectral-Inspired Graph Neural Networks

This repo contains implementations of spectral-inspired GNNs, a simple layer-wise normalization technique to inject global information in message-passing GNNs, motivated from spectral graph embedding.

## Dependencies
- Python 3.7+
- Pytorch 1.10+
- [pytorch-geometric](https://pytorch-geometric.readthedocs.io/en/latest/notes/installation.html)
- [dgl-cu111](https://docs.dgl.ai/en/latest/install/index.html)


You can follow the code below to install pytorch-geometric
```
import os
import torch
os.environ['TORCH'] = torch.__version__
pip install -q torch-scatter -f https://data.pyg.org/whl/torch-${TORCH}.html
pip install -q torch-sparse -f https://data.pyg.org/whl/torch-${TORCH}.html
pip install -q torch-cluster -f https://data.pyg.org/whl/torch-${TORCH}.html
pip install -q git+https://github.com/pyg-team/pytorch_geometric.git
```

Follow the code below to install dgl
```
pip install dgl-cu111 -f https://data.dgl.ai/wheels/repo.html
```

## PowerEmbed
Run PowerEmbed on the 10 benchmark graphs with the default implementation:
```
python power.py --datasets wiki --loop --data_path YOUR_DATA_PATH --result_path YOUR_RESULT_PATH
```
datasets include options with: wiki / planetoid / webkb / amazon / coauthor

## Baseline
Run GCNII, GPR-GNN and JKNet on the 10 benchmark graphs with the default implementation:
```
python /baseline/gcn_variants_real_graph.py --datasets wiki --loop --model GCNII --data_path YOUR_DATA_PATH --result_path YOUR_RESULT_PATH
```
datasets include options with: wiki / planetoid / webkb / amazon / coauthor

models include options with: GCNII / GPRGNN / JKNet

## Simulations and visualizations
- Convergence of PowerEmbed
  - Fig 2: ```power_convergence.ipynb```
- SBM simulations
  - Fig 3, 5: ```/ablation study/sbm_boxplot.py```
  - Fig 6: ```/ablation study/sbm_varying_density.py```
    
