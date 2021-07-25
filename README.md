# Seeing through Obstruction with Layer Decomposition (SOLD)

<img src='./teaser.jpg' width=1000>

We present a learning-based approach for removing unwanted obstructions, such as window reflections, fence occlusions, or raindrops, from a short sequence of images captured by a moving camera. Our method leverages motion differences between the background and obstructing elements to recover both layers. Specifically, we alternate between estimating dense optical flow fields of the two layers and reconstructing each layer from the flow-warped images via a deep convolutional neural network. This learning-based layer reconstruction module facilitates accommodating potential errors in the flow estimation and brittle assumptions, such as brightness consistency. We show that the proposed approach learned from synthetically generated data performs well to real images. Experimental results on numerous challenging scenarios of reflection and fence removal demonstrate the effectiveness of the proposed method.

[[Project]](https://alex04072000.github.io/SOLD/)

Paper

<a href="https://arxiv.org/abs/2008.04902" rel="Paper"><img src="thumb.jpg" alt="Paper" width="100%"></a>

## Overview
This is the author's reference implementation of the multi-image reflection/fence removal using TensorFlow described in:
"Learning to See Through Obstructions with Layered Decomposition"
[Yu-Lun Liu](http://www.cmlab.csie.ntu.edu.tw/~yulunliu/), [Wei-Sheng Lai](https://www.wslai.net/), [Ming-Hsuan Yang](https://faculty.ucmerced.edu/mhyang/), [Yung-Yu Chuang](https://www.csie.ntu.edu.tw/~cyy/), [Jia-Bin Huang](https://filebox.ece.vt.edu/~jbhuang/) (National Taiwan University & Google & Virginia Tech & University of California at Merced & MediaTek Inc.)
If you find this code useful for your research, please consider citing the following paper.

Further information please contact [Yu-Lun Liu](http://www.cmlab.csie.ntu.edu.tw/~yulunliu/).

## Requirements setup
* [TensorFlow](https://www.tensorflow.org/):

    * tested using TensorFlow 1.10.0

* [Pre-trained PWC-Net](https://github.com/philferriere/tfoptflow)
    * Please overwrite `tfoptflow/model_pwcnet.py` and `tfoptflow/model_base.py` using the ones in this repository.

* To download the pre-trained models:

    * [ckpt](https://drive.google.com/file/d/17jtbioClXI_bj1ES5k71zI_Q9uoKQJLi/view?usp=sharing)

## Data Preparation
Please prepare 5 frames and follow the naming rule `XXXXX_I[0-4].png` as shown in `reflection_imgs` or `fence_imgs` folder, and change the folder path in `run_reflection.py` or `run_fence.py`.

## Usage
* Run your own sequence (reflection removal):
``` bash
CUDA_VISIBLEDEVICES=0 python3 run_reflection.py
```

* Run your own sequence (fence removal):
``` bash
CUDA_VISIBLEDEVICES=0 python3 run_fence.py
```

## Google Colab Demo
https://colab.research.google.com/drive/1kCG5SJd3usgzi6Bx979KiaO_YTanNVVz?usp=sharing

## Collected Controlled Sequences
We collect six sequences with ground truth.
* website/Obstruction_HTML_CameraReady/results/reflection/Huang and Liu/00071
* website/Obstruction_HTML_CameraReady/results/reflection/Huang and Liu/00072
* website/Obstruction_HTML_CameraReady/results/fence/Huang and Liu/00006
* website/Obstruction_HTML_CameraReady/results/fence/Huang and Liu/00007
* website/Obstruction_HTML_CameraReady/results/fence/Huang and Liu/00008
* website/Obstruction_HTML_CameraReady/results/raindrop/Huang and Liu/00005

## Citation
```
[1] Yu-Lun Liu, Wei-Sheng Lai, Ming-Hsuan Yang, Yung-Yu Chuang, and Jia-Bin Huang. Learning to See Through Obstructions with Layered Decomposition. arXiv, 2020
```
