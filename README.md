# stable-baselines-tf2
The original [stable-baselines](https://github.com/hill-a/stable-baselines) repo only supports TF1.x.\
This repo makes a few modifications to make stable-baselines compatible with TF2.x while keeping the rest of the code logic intact.

## Features Introduced Not Exist In Stable Baselines
- L2 regularization in `PPO2`. Set L2 loss weight to zero if you want to turn off regularization.

## Installation Instruction
- Follow the instructions in the [original repo](https://github.com/hill-a/stable-baseline) to install stable-baselines;
- Locate the original `stable_baselines/` folder on your machine and remove that folder:
```
path=$(find . -type d -name "stable_baselines")
rm -r $path
```
- Download (`git clone`) this repo, and copy its content to where `stable_baselines/` used to locate:
```
cp stable-baselines-tf2/* $path
```
- Delete the downloaded repo:
```
rm -r stable-baselines-tf2
```
