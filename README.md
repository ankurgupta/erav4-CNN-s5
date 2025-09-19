# erav4-CNN-s5
MNIST Neural Network

# Compact CNN for MNIST Classification

This project implements a compact Convolutional Neural Network (CNN) in PyTorch for classifying MNIST handwritten digits.  
The network is optimized to stay under ~25k parameters while still achieving **95%+ accuracy**.

---

## 📌 Features
- **Lightweight CNN (<25k params)**  
- **Batch Normalization** for stable training  
- **Dropout (0.1)** for regularization  
- **Global Average Pooling (GAP)** to minimize fully connected parameters  
- **SGD with Momentum** optimizer  
- Training & Testing loops with **progress bar (tqdm)**

---

## 🏗️ Model Architecture
Input: 1 x 28 x 28
→ Conv2d(1, 16, 3x3) → ReLU → BN → Dropout
→ Conv2d(16, 32, 3x3) → ReLU → BN → Dropout
→ Conv2d(32, 10, 1x1) → MaxPool(2x2)
→ Conv2d(10, 16, 3x3) → ReLU → BN → Dropout
→ Conv2d(16, 16, 3x3) → ReLU → BN → Dropout
→ Conv2d(16, 16, 3x3) → ReLU → BN → Dropout
→ Global Avg Pooling (GAP)
→ Flatten → Linear(16 → 10)
→ LogSoftmax



GPU available: True

## 🏗️ Architecture

| Layer (type)        | Output Shape        | Param # |
|----------------------|---------------------|---------|
| Conv2d-1            | [-1, 16, 26, 26]   | 160     |
| BatchNorm2d-2       | [-1, 16, 26, 26]   | 32      |
| Dropout-3           | [-1, 16, 26, 26]   | 0       |
| Conv2d-4            | [-1, 32, 24, 24]   | 4,640   |
| BatchNorm2d-5       | [-1, 32, 24, 24]   | 64      |
| Dropout-6           | [-1, 32, 24, 24]   | 0       |
| Conv2d-7            | [-1, 10, 24, 24]   | 330     |
| MaxPool2d-8         | [-1, 10, 12, 12]   | 0       |
| Conv2d-9            | [-1, 16, 10, 10]   | 1,456   |
| BatchNorm2d-10      | [-1, 16, 10, 10]   | 32      |
| Dropout-11          | [-1, 16, 10, 10]   | 0       |
| Conv2d-12           | [-1, 16, 8, 8]     | 2,320   |
| BatchNorm2d-13      | [-1, 16, 8, 8]     | 32      |
| Dropout-14          | [-1, 16, 8, 8]     | 0       |
| Conv2d-15           | [-1, 16, 6, 6]     | 2,320   |
| BatchNorm2d-16      | [-1, 16, 6, 6]     | 32      |
| Dropout-17          | [-1, 16, 6, 6]     | 0       |
| AdaptiveAvgPool2d-18| [-1, 16, 1, 1]     | 0       |
| Linear-19           | [-1, 10]           | 170     |

---

## 📌 Model Stats

- **Total params:** 11,588  
- **Trainable params:** 11,588  
- **Non-trainable params:** 0  

---

## 💾 Memory Usage

- **Input size (MB):** 0.00  
- **Forward/backward pass size (MB):** 0.80  
- **Params size (MB):** 0.04  
- **Estimated Total Size (MB):** 0.85  




Epoch 1 [Training]: 100%|██████████| 469/469 [00:16<00:00, 28.02it/s, accuracy=87.7, loss=0.109]
Training Epoch 1: Avg loss: 0.4473, Accuracy: 52665/60000 (87.78%)

Testing Epoch 1: Avg loss: 0.0835, Accuracy: 9766/10000 (97.66%)

Epoch 2 [Training]: 100%|██████████| 469/469 [00:15<00:00, 29.35it/s, accuracy=97.7, loss=0.0662]
Training Epoch 2: Avg loss: 0.0792, Accuracy: 58677/60000 (97.80%)

Testing Epoch 2: Avg loss: 0.0697, Accuracy: 9802/10000 (98.02%)

Epoch 3 [Training]: 100%|██████████| 469/469 [00:16<00:00, 28.32it/s, accuracy=98.2, loss=0.0228]
Training Epoch 3: Avg loss: 0.0619, Accuracy: 58940/60000 (98.23%)

Testing Epoch 3: Avg loss: 0.0428, Accuracy: 9865/10000 (98.65%)

Epoch 4 [Training]: 100%|██████████| 469/469 [00:15<00:00, 29.49it/s, accuracy=98.3, loss=0.0411]
Training Epoch 4: Avg loss: 0.0536, Accuracy: 59036/60000 (98.39%)

Testing Epoch 4: Avg loss: 0.0333, Accuracy: 9897/10000 (98.97%)

Epoch 5 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.17it/s, accuracy=98.6, loss=0.0202]
Training Epoch 5: Avg loss: 0.0455, Accuracy: 59198/60000 (98.66%)

Testing Epoch 5: Avg loss: 0.0289, Accuracy: 9910/10000 (99.10%)

Epoch 6 [Training]: 100%|██████████| 469/469 [00:17<00:00, 27.34it/s, accuracy=98.6, loss=0.0177]
Training Epoch 6: Avg loss: 0.0428, Accuracy: 59208/60000 (98.68%)

Testing Epoch 6: Avg loss: 0.0399, Accuracy: 9872/10000 (98.72%)

Epoch 7 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.19it/s, accuracy=98.8, loss=0.0181]
Training Epoch 7: Avg loss: 0.0389, Accuracy: 59301/60000 (98.83%)

Testing Epoch 7: Avg loss: 0.0307, Accuracy: 9901/10000 (99.01%)

Epoch 8 [Training]: 100%|██████████| 469/469 [00:16<00:00, 28.95it/s, accuracy=98.8, loss=0.0203]
Training Epoch 8: Avg loss: 0.0358, Accuracy: 59324/60000 (98.87%)

Testing Epoch 8: Avg loss: 0.0268, Accuracy: 9911/10000 (99.11%)

Epoch 9 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.17it/s, accuracy=98.9, loss=0.0264]
Training Epoch 9: Avg loss: 0.0346, Accuracy: 59365/60000 (98.94%)

Testing Epoch 9: Avg loss: 0.0282, Accuracy: 9904/10000 (99.04%)

Epoch 10 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.25it/s, accuracy=98.9, loss=0.0531]
Training Epoch 10: Avg loss: 0.0325, Accuracy: 59363/60000 (98.94%)

Testing Epoch 10: Avg loss: 0.0275, Accuracy: 9904/10000 (99.04%)

Epoch 11 [Training]: 100%|██████████| 469/469 [00:17<00:00, 26.89it/s, accuracy=99, loss=0.0982]
Training Epoch 11: Avg loss: 0.0311, Accuracy: 59427/60000 (99.05%)

Testing Epoch 11: Avg loss: 0.0269, Accuracy: 9915/10000 (99.15%)

Epoch 12 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.30it/s, accuracy=99, loss=0.0516]

Training Epoch 12: Avg loss: 0.0298, Accuracy: 59458/60000 (99.10%)
Testing Epoch 12: Avg loss: 0.0269, Accuracy: 9903/10000 (99.03%)

Epoch 13 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.01it/s, accuracy=99, loss=0.014]
Training Epoch 13: Avg loss: 0.0288, Accuracy: 59461/60000 (99.10%)

Testing Epoch 13: Avg loss: 0.0268, Accuracy: 9912/10000 (99.12%)

Epoch 14 [Training]: 100%|██████████| 469/469 [00:15<00:00, 29.51it/s, accuracy=99, loss=0.025]
Training Epoch 14: Avg loss: 0.0284, Accuracy: 59446/60000 (99.08%)

Testing Epoch 14: Avg loss: 0.0219, Accuracy: 9926/10000 (99.26%)

Epoch 15 [Training]: 100%|██████████| 469/469 [00:15<00:00, 29.89it/s, accuracy=99.1, loss=0.0157]
Training Epoch 15: Avg loss: 0.0263, Accuracy: 59498/60000 (99.16%)

Testing Epoch 15: Avg loss: 0.0243, Accuracy: 9915/10000 (99.15%)

Epoch 16 [Training]: 100%|██████████| 469/469 [00:16<00:00, 27.97it/s, accuracy=99.1, loss=0.00817]
Training Epoch 16: Avg loss: 0.0264, Accuracy: 59488/60000 (99.15%)

Testing Epoch 16: Avg loss: 0.0244, Accuracy: 9921/10000 (99.21%)

Epoch 17 [Training]: 100%|██████████| 469/469 [00:15<00:00, 29.81it/s, accuracy=99.1, loss=0.00925]
Training Epoch 17: Avg loss: 0.0251, Accuracy: 59518/60000 (99.20%)

Testing Epoch 17: Avg loss: 0.0214, Accuracy: 9927/10000 (99.27%)

Epoch 18 [Training]: 100%|██████████| 469/469 [00:15<00:00, 30.16it/s, accuracy=99.2, loss=0.0102]
Training Epoch 18: Avg loss: 0.0236, Accuracy: 59563/60000 (99.27%)

Testing Epoch 18: Avg loss: 0.0214, Accuracy: 9927/10000 (99.27%)

Epoch 19 [Training]: 100%|██████████| 469/469 [00:16<00:00, 29.31it/s, accuracy=99.2, loss=0.0294]
Training Epoch 19: Avg loss: 0.0234, Accuracy: 59569/60000 (99.28%)

Testing Epoch 19: Avg loss: 0.0206, Accuracy: 9927/10000 (99.27%)

Epoch 20 [Training]: 100%|██████████| 469/469 [00:15<00:00, 30.34it/s, accuracy=99.2, loss=0.0134]
Training Epoch 20: Avg loss: 0.0237, Accuracy: 59547/60000 (99.25%)

Testing Epoch 20: Avg loss: 0.0210, Accuracy: 9928/10000 (99.28%)

==================================================
Training complete!
Best Training Accuracy: 99.28%
Best Testing Accuracy: 99.28%
==================================================
