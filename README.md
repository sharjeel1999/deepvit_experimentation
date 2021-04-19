# DeepViT

This repo is the official implementation of ["DeepViT: Towards Deeper Vision Transformer"](https://arxiv.org/abs/2103.11886). The repo is based on the timm library (https://github.com/rwightman/pytorch-image-models) by [Ross Wightman](https://github.com/rwightman)

## Introduction

**Deep Vision Transformer** is initially described in [arxiv](https://arxiv.org/abs/2103.11886), which observes the attention collapese phenomenon when training deep vision transformers: In this paper, we show that, unlike convolution neural networks (CNNs)that can be improved by stacking more convolutional layers, the performance of ViTs saturate fast when scaled to be deeper. More specifically, we empirically observe that such scaling difficulty is caused by the attention collapse issue: as the transformer goes deeper, the attention maps gradually become similar and even much the same after certain layers. In other words, the feature maps tend to be identical in the top layers of deep ViT models. This fact demonstrates that in deeper layers of ViTs, the self-attention mechanism fails to learn effective concepts for representation learning and hinders the model from getting expected performance gain. Based on above observation, we propose a simple yet effective method, named Re-attention, to re-generate the attention maps to increase their diversity at different layers with negligible computation and memory cost. The pro-posed method makes it feasible to train deeper ViT models with consistent performance improvements via minor modification to existing ViT models. Notably, when training a deep ViT model with 32 transformer blocks, the Top-1 classification accuracy can be improved by 1.6% on ImageNet.

<p align="center">
<img src="https://github.com/zhoudaquan/DeepViT_ICCV21/blob/master/figures/performance_comparison.png" | width=500>
</p>

## 2. DeepViT Models

1. Comparison with ViTs
| Model        | Re-attention | Top1 Acc (%) | #Params | #Similar Blocks |  Checkpoint | Attention Map |
| :---         |   :---:         |  :---:   |  :---:  | :---: |  :---:   | :---:   | 
| ViT-16       |  NA  |   78.88   |  24.5M  | 5 | [here](comming soon)| |
| DeepViT-16   |  FC  |   79.10   |  24.5M  | 0  | [here](comming soon)|  |
| ViT-24       |  NA  |   79.35   |  36.3M  | 11  | [here](comming soon)|  |
| DeepViT-24   |  FC  |   79.99   |  36.3M  | 0  | [here](comming soon)|  |
| ViT-32       | NA   |   79.27   |  48.1M  | 15 | [here](comming soon)  |  |
| DeepViT-32 | FC   |   80.90   |  48.1M  | 0  | [here](comming soon) |  |


## Citing DeepVit

```
@article{zhou2021deepvit,
  title={DeepViT: Towards Deeper Vision Transformer},
  author={Zhou, Daquan and Kang, Bingyi and Jin, Xiaojie and Yang, Linjie and Lian, Xiaochen and Hou, Qibin and Feng, Jiashi},
  journal={arXiv preprint arXiv:2103.11886},
  year={2021}
}
```




