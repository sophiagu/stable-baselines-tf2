# stable-baselines-tf2
The original [stable-baselines](https://github.com/hill-a/stable-baselines) repo only supports TF1.x.\
This repo makes a few modifications to make stable-baselines compatible with TF2.x while keeping the rest of the code logic intact.

## Features Introduced Not Exist In Stable Baselines
L1 and L2 regularizations are introduced in `PPO2`. You may mimic them to apply to other agents, e.g., A2C.\
In general, the network performs better with regularizations. You can tune the L1 and L2 weights based on the following quick facts:
  - L1 regularization makes the network weights sparse;
  - L2 regularization makes the network weights small.

## Installation Instruction
- Follow the instructions in the [original repo](https://github.com/hill-a/stable-baselines) to install `stable-baselines`;
- Locate the original `stable_baselines/` folder on your machine and remove that folder (depending on your machine and environment types, you may need to use other ways to locate this folder):
```
path=$(find . -type d -name "stable_baselines")
echo $path
rm -r $path
```
- Download (`git clone`) this repo, and copy its content to where `stable_baselines/` used to locate:
```
mkdir $path
cp -r stable-baselines-tf2/* $path
```
- Check all the files are coped to `$path`:
```
ls $path
```
- Delete the downloaded repo (and answer `y` to all questions):
```
rm -r stable-baselines-tf2
```

## Notes
- This repo does not work with `tensorboard` yet due to some weird compatibility issues for `tf.summary` in TF1.
