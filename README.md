# CGNet: A Light-weight Context Guided Network for Semantic Segmentation
## Introduction
The demand of applying semantic segmentation model on mobile devices has been increasing rapidly. Current state-of-the-art networks have enormous amount of parameters hence unsuitable for mobile devices, while other small memory footprint models ignore the inherent characteristicof semantic segmentation. To tackle this problem, we propose a novel Context Guided Network (CGNet), which is a light-weight network for semantic segmentation on mobile devices. We first propose the Context Guided (CG) block, which learns the joint feature of both local feature and surrounding context, and further improves the joint feature with the global context. Based on the CG block, we develop Context Guided Network (CGNet), which captures contextual information in all stages of the network and is specially tailored for increasing segmentation accuracy. CGNet is also elaborately designed to reduce the number of parameters and save memory footprint. Under an equivalent number of parameters, the proposed CGNet significantly outperforms existing segmentation networks. Extensive experiments on Cityscapes and CamVid datasets verify the effectiveness of the proposed approach. Specifically, without any post-processing, CGNet achieves 64.8% mean IoU on Cityscapes with less than 0.5 M parameters, and has a frame-rate of 50 fps on one NVIDIA Tesla K80 card for 2048 × 1024 high-resolution images.


## [Results](https://www.cityscapes-dataset.com/method-details/?submissionID=2095&back=mysubmissions) on Cityscapes test set
We train the proposed CGNet with only fine annotated data and submit our test results to the official evaluation server.
![image](img/results_on_cityscapes.png)

## Usage
1. Install PyTorch
  - The code is developed on python3.6.5 on Ubuntu 16.04. (GPU: Tesla K80; PyTorch: 0.5.0a0+9b0cece; Cuda: 8.0)
2. Clone the repository
   ```shell
   git clone https://github.com/wutianyiRosun/CGNet.git 
   cd CGNet
   ```
3. Dataset

  - Download the [Cityscapes](https://www.cityscapes-dataset.com/) dataset and convert the dataset to [19 categories](https://github.com/mcordts/cityscapesScripts/blob/master/cityscapesscripts/helpers/labels.py). 
  
4. Training
  ```
    python train.py
  ```
5. Evaluation (on validation set)
 
  ```
    python eval.py
  ```
6. Testing (on test set)
  ```
    python test.py
  ```