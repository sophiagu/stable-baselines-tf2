# stable-baselines-tf2
The original [stable-baselines](https://github.com/hill-a/stable-baselines) repo only supports TF1.x.\
This repo makes a few modifications to make stable-baselines compatible with TF2.x while keeping the rest of the code logic intact.

## Features Introduced Not Exist In Stable Baselines
- In general, the network performs better with regularizations. L1 and L2 regularizations are introduced in `PPO2`. Feel free to tune the L1 and L2 weights based on your problem (You can also mimic them to apply to other agents, e.g., A2C);
- New Policies: `ConvexPolicy` which uses a policy network whose output is convex w.r.t. the input corresponding to the last dim of the observation space; `SigmoidMlpPolicy` which adds a linear layer with sigmoid activation before the original feedforward network.

## Installation Instruction
- Follow the instructions in the [original repo](https://github.com/hill-a/stable-baseline) to install `stable-baselines`;
- Locate the original `stable_baselines/` folder on your machine and remove that folder:
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
- This deposit does not work with `tensorboard` yet due to some weird compatibility issues for `tf.summary` in TF1.
