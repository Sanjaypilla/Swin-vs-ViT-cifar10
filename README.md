# Swin Transformer vs Vision Transformer on CIFAR-10

This project presents a comparative analysis between two state-of-the-art transformer-based architectures for computer vision — **Swin Transformer** and **Vision Transformer (ViT)** — applied to the CIFAR-10 image classification task.


## Objective

To evaluate and compare **Swin Transformer** and **ViT** in terms of:
- Classification accuracy
- Training behavior (loss, convergence speed)
- Model complexity and architectural differences
- Practical performance on the CIFAR-10 dataset


## Architectures Overview

### Vision Transformer (ViT)
- Flat structure with fixed-size patches
- Global self-attention across all patches
- Requires absolute positional encoding
- Lacks native multi-scale feature extraction

### Swin Transformer
- Hierarchical architecture with multi-stage processing
- Local attention within windows (W-MSA) and shifted windows (SW-MSA)
- Relative positional bias enhances translation invariance
- Naturally supports tasks like object detection and segmentation due to hierarchical outputs


## Comparison Summary

| Feature                    | Vision Transformer (ViT)   | Swin Transformer             |
|---------------------------|-----------------------------|------------------------------|
| Architecture              | Flat, single-scale          | Hierarchical, multi-scale    |
| Attention Type            | Global Self-Attention       | Window-based with shift      |
| Positional Encoding       | Absolute                    | Relative (within windows)    |
| Computational Complexity  | O(N²)                       | O(N)                         |
| Object Detection          | Needs additional heads      | Native support               |
| Semantic Segmentation     | Not optimized               | Strong performance           |
| ImageNet Top-1 Accuracy   | ~77.9% (ViT-B/16)           | 86.4% (Swin-B)               |
| COCO Detection (Box AP)   | ~45–50                      | 58.7                         |
| ADE20K mIoU               | ~47                         | 53.5                         |


## Visual Analysis
![Swin Acc](https://github.com/user-attachments/assets/97ac5aa1-ded8-42fb-8a72-4df443dfe886)
![Swin loss](https://github.com/user-attachments/assets/8d09ede4-4551-475a-9425-b73c1944519e)
![Vit Acc](https://github.com/user-attachments/assets/2afc67cf-3168-441f-b66f-47d4dc4b8fed)
![Vit loss](https://github.com/user-attachments/assets/ed157671-04f9-4f6c-b26b-1dc21f1485b1)
![Swin vs vit accu](https://github.com/user-attachments/assets/99d6317e-4d89-440b-9d35-9dc8bd541630)
![swin vs vit loss](https://github.com/user-attachments/assets/936d48af-5a90-4398-a9ae-5b339f743504)


## CIFAR-10 Results (Your Experiment)

| Metric            | Swin Transformer | Vision Transformer |
|------------------|------------------|--------------------|
| **Test Accuracy** | 90.46%           | **91.65%**         |
| **Train Accuracy**| 67.89%           | 70.35%             |
| **Test Loss**     | 0.3056           | **0.2875**         |

### Analysis
- ViT outperforms Swin Transformer in all key metrics on CIFAR-10 under identical conditions.
- Swin shows slower convergence, indicating more stable but gradual learning.
- ViT reaches higher accuracy and lower loss by epoch 200, making it more effective in this setup.


