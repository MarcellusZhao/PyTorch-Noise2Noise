# EE-559 Project: Learning Image Restoration without Clean Data
****The README outlines the requirements, project structure and the way to reproduce our final results. For more details, please check our report.****

Table of Contents
---

* [Introduction](#introduction)
* [Requirements](#requirements)
* [Project Structure](#project structure)
* [How to run](#how to run)
* [Results](#results)

Introduction
---

This project aims to implement a Noise2Noise model. A Noise2Noise model is an image denoising network trained without a clean reference image. The original paper can be found [here](https://arxiv.org/abs/1803.04189).

The project has two parts, focusing on two dierent facets of deep learning. The rst one is to build a network
that denoises using the PyTorch framework, in particular the torch.nn modules and autograd. The second one
is to understand and build a framework, its constituent modules, that are the standard building blocks of deep
networks without PyTorch's autograd.

Requirements
---



Project Structure
---

Here is an overview of the architecture of our project:

```
|--Miniproject_1
	|--__init__.py
	|--model.py
	|--bestmodel.pth
	|--Report_1.pdf
	|--others
		|--__init__.py
		|--config.py
		|--datasets.py
		|--networks.py
		|--train_example.py
		|--utils.py
|--Miniproject_2
	|--__init__.py
	|--model.py
	|--bestmodel.pth
	|--Report_2.pdf
	|--others
		|--helpers.py
		|--NNUsampling_conv.py
|--data
	|--train_data.pkl
	|--val_data.pkl
|--results
|--README.md
		
```

How to run
---

We used the GPU, provided by VITA lab, to run our model. It is also possible to run our model with CPU, but it would be time-consuming.

To reproduce our final results or train from scratch (You can use the data provided in this repo and skip step 1&2, or use your own data):

1. Upload your own data and make sure they are in directory `./data/`.

2. Split the data into training set and validation set, and name them as in project structure.

3. Play with the model using `./Miniproject/others/train_example.py`:

   1. use default model parameters to train and evaluate the model from scratch by running:

   ```
   cd Miniproject/others
   python train_example.py
   ```

   2. If you have pretrained checkpoint, set `resume` argument as `True` and place the checkpoint in directory `./Miniproject/bestmodel.pth`.

4. In `./Miniproject_2/model.py`,  we provide self-implemented modules widely used in Convolutional Neural Network (CNN), such as Conv2d, Upsampling, SGD, and MaxPool2d layers. The forward and backward processes are self-contained.

Results
---

<p align="center">
  <img src="Results/group.png" height="370">
</p>
