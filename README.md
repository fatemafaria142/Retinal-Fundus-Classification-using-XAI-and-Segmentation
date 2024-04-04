# Retinal-Fundus-Classification-using-XAI-and-Segmentation

## Abstract
Our research focuses on the critical field of early diagnosis of disease by examining retinal blood vessels in fundus images. While automatic segmentation of retinal blood vessels holds promise for early detection, accurate analysis remains challenging due to the limitations of existing methods, which often lack discrimination power and are susceptible to influences from pathological regions. Our research in fundus image analysis advances deep learning-based classification using eight pre-trained CNN models. To enhance interpretability, we utilize Explainable AI techniques such as Grad-CAM, Grad-CAM++, Score-CAM, Faster Score-CAM, and Layer CAM. These techniques illuminate the decision-making processes of the models, fostering transparency and trust in their predictions. Expanding our exploration, we investigate ten models, including TransUNet with ResNet backbones, Attention U-Net with DenseNet and ResNet backbones, and Swin-UNET. Incorporating diverse architectures such as ResNet50V2, ResNet101V2, ResNet152V2, and DenseNet121 among others, this comprehensive study deepens our insights into attention mechanisms for enhanced fundus image analysis. Among the evaluated models for fundus image classification, ResNet101 emerged with the highest accuracy, achieving an impressive 94.17\%. On the other end of the spectrum, EfficientNetB0 exhibited the lowest accuracy among the models, achieving a score of 88.33\%. Furthermore, in the domain of fundus image segmentation, Swin-Unet demonstrated a Mean Pixel Accuracy of 86.19\%, showcasing its effectiveness in accurately delineating regions of interest within fundus images. Conversely, Attention U-Net with DenseNet201 backbone exhibited the lowest Mean Pixel Accuracy among the evaluated models, achieving a score of 75.87\%. The presented findings contribute valuable insights to the performance and interpretability of deep learning models in fundus image analysis, offering advancements in medical image understanding and diagnosis.

## Table of Contents
- [Proposed Methodology](#experimental-methodology)
- [Experimental Setups](#experimental-setups)
- [Dataset Availability](#dataset-availability)
- [Results](#results)
- [Citation](#citation)
- [Contact Information](#contact-information)

## Proposed Methodology
![Methodology](Retina_Fundus.jpeg)

## Experimental Setups

### Setup 1: Kaggle
- **Environment:**
  - Python Version: 3.11
  - PyTorch Version: 2.1.0
  - GPU: T4 GPU with 7.5 Compute Capability
  - RAM: 30 GB

### Setup 2: Jupyter Notebook Environment
- **Environment:**
  - Python Version: 3.10.12
  - Tensforflow Version: 2.6.0
  - GPU: NVIDIA GeForce RTX 3050 (8 GB)
  - RAM: 16 GB
  - Storage: 512 GB NVMe SSD
    
### Setup 3: Jupyter Notebook Environment
- **Environment:**
  - Python Version: 3.10.12
  - Tensforflow Version: 2.6.0
  - GPU: NVIDIA GeForce RTX 3060 (8 GB)
  - RAM: 16 GB
  - Storage: 512 GB NVMe SSD
    
## Dataset Availability

For classification purposes, the FIVES Database was employed, while for segmentation tasks, two databases were utilized: DRIVE and FIVES. 


## Results
### Performance Evaluation of Pretrained CNNs for Fundus Image Classification

| Model             | Accuracy | Precision | Recall  | F1 Score | Jaccard Score | Log Loss |
|-------------------|----------|-----------|---------|----------|---------------|----------|
| ResNet101         | 0.9417   | 0.9435    | 0.9417  | 0.9418   | 0.8902        | 0.2254   |
| DenseNet169       | 0.9333   | 0.9378    | 0.9333  | 0.9333   | 0.8751        | 0.9080   |
| Xception          | 0.9250   | 0.9284    | 0.9250  | 0.9252   | 0.8612        | 1.3931   |
| InceptionV3       | 0.9167   | 0.9203    | 0.9167  | 0.9166   | 0.8480        | 0.8012   |
| DenseNet121       | 0.9083   | 0.9092    | 0.9083  | 0.9075   | 0.8320        | 4.5509   |
| InceptionResNetV2 | 0.9000   | 0.9049    | 0.9000  | 0.9008   | 0.8202        | 12.0282  |
| ResNet50          | 0.8917   | 0.8948    | 0.8917  | 0.8926   | 0.8089        | 0.4883   |
| EfficientNetB0    | 0.8833   | 0.8862    | 0.8833  | 0.8837   | 0.7947        | 0.6697   |



### U-Net Variants Performance Assessment for Retinal Blood Vessel Segmentation

#### Using the DRIVE Dataset 

| Models          | Backbone           | Intersection over Union (IoU) | Dice Coefficient | Mean Pixel Accuracy | Mean Modified Hausdorff Distance | Mean Surface Dice Overlap |
|-----------------|--------------------|--------------------------------|------------------|---------------------|----------------------------------|---------------------------|
| TransUNET       | ResNet50V2         | 0.5273                         | 0.6899           | 0.6470              | 3.852                            | 0.0151                    |
|                 | ResNet101V2        | 0.5169                         | 0.6803           | 0.6400              | 4.0864                           | 0.0188                    |
|                 | ResNet152V2        | 0.5250                         | 0.6879           | 0.6514              | 4.052                            | 0.0167                    |
| Attention U-Net | ResNet50V2         | 0.6460                         | 0.7848           | 0.7953              | 2.7150                           | 0.0070                    |
|                 | ResNet101V2        | 0.6483                         | 0.7865           | 0.8023              | 2.7341                           | 0.0054                    |
|                 | ResNet152V2        | 0.6474                         | 0.7859           | 0.7859              | 2.6718                           | 0.0069                    |
|                 | DenseNet121        | 0.6427                         | 0.7824           | 0.7747              | 2.7484                           | 0.0090                    |
|                 | DenseNet169        | 0.6444                         | 0.7837           | 0.7769              | 2.6776                           | 0.0072                    |
|                 | DenseNet201        | 0.6422                         | 0.7827           | 0.7749              | 2.6475                           | 0.0074                    |
| Swin-UNET       | Swin Transformer   | 0.4896                         | 0.6569           | 0.6062              | 4.3675                           | 0.0178                    |

#### Using the FIVES Dataset 

| Models          | Backbone           | Intersection over Union (IoU) | Dice Coefficient | Mean Pixel Accuracy | Mean Modified Hausdorff Distance | Mean Surface Dice Overlap |
|-----------------|--------------------|--------------------------------|------------------|---------------------|----------------------------------|---------------------------|
| TransUNET       | ResNet50V2         | 0.6436                         | 0.7791           | 0.7758              | 3.7392                           | 0.0312                    |
|                 | ResNet101V2        | 0.6559                         | 0.7898           | 0.7764              | 3.5491                           | 0.0285                    |
|                 | ResNet152V2        | 0.6522                         | 0.7866           | 0.7696              | 3.5278                           | 0.0319                    |
| Attention U-Net | ResNet50V2         | 0.7175                         | 0.8353           | 0.8512              | 2.8913                           | 0.0201                    |
|                 | ResNet101V2        | 0.7221                         | 0.8385           | 0.8507              | 2.8009                           | 0.0223                    |
|                 | ResNet152V2        | 0.7199                         | 0.8369           | 0.8331              | 2.8134                           | 0.0378                    |
|                 | DenseNet121        | 0.6872                         | 0.8143           | 0.7866              | 3.2814                           | 0.0591                    |
|                 | DenseNet169        | 0.6718                         | 0.8024           | 0.8115              | 3.5513                           | 0.0235                    |
|                 | DenseNet201        | 0.6468                         | 0.7822           | 0.7587              | 3.6267                           | 0.0293                    |
| Swin-UNET       | Swin Transformer   | 0.5179                         | 0.6765           | 0.5987              | 4.6090                           | 0.0891                    |

### Comparative Analysis of Explainable AI Methods
![Results](Retina_Fundus_XAI.jpeg)


## Contact Information

For any questions, collaboration opportunities, or further inquiries, please feel free to reach out:

- **Fatema Tuj Johora Faria**
  - Email: [fatema.faria142@gmail.com](mailto:fatema.faria142@gmail.com)

- **Mukaffi Bin Moin**
  - Email: [mukaffi28@gmail.com](mailto:mukaffi28@gmail.com)

- **Pronay Debnath**
  - Email: [pronaydebnath99@gmail.com](mailto:pronaydebnath99@gmail.com)
- **Asif Iftekher Fahim**
  - Email: [fahimthescientist@gmail.com](mailto:fahimthescientist@gmail.com)
    
## Citation

If you find the dataset or the associated research work helpful, please consider citing our paper:

```bibtex
@misc{faria2023vashantor,
  title={Vashantor: A Large-scale Multilingual Benchmark Dataset for Automated Translation of Bangla Regional Dialects to Bangla Language},
  author={Fatema Tuj Johora Faria and Mukaffi Bin Moin and Ahmed Al Wase and Mehidi Ahmmed and Md. Rabius Sani and Tashreef Muhammad},
  year={2023},
  eprint={2311.11142},
  archivePrefix={arXiv},
  primaryClass={cs.CL}
}

