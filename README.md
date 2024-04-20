This is a contemporary PyTorch implementation of the Dreamer v1 algorithm, originally
developed by Danijar Hafner et al. The original paper is
accessible [here](https://danijar.com/project/dreamer/).

This implementation draws heavily from the following projects:

- [The original Dreamer v1 implementation](https://github.com/danijar/dreamer)
- [dreamer-pytorch by Julius Frost](https://github.com/juliusfrost/dreamer-pytorch)
- [dreamer-pytorch by Yusuke Urakami](https://github.com/yusukeurakami/dreamer-pytorch)

The purpose of this project is solely for academic use.

Additionally, this project serves as a supplementary project for
our [CSC413 final project](https://github.com/csc413-project/csc413-project) at the
University of Toronto, where I am collaborating with the following wonderful people:

- [Charlotte](https://github.com/CharlotteChenyy)
- [Blair](https://github.com/blairyeung)
- [Ray](https://github.com/Lei-Tin)

Feel free to reach me out at `ScottCTD@outlook.com`.

# Reproduce Results

| Task             | Original Dreamer | Our Dreamer    |
|------------------|------------------|----------------|
| Acrobot Swingup  | ~260             | 269            |
| Cartpole Swingup | ~760             | 771            |
| Cheetah Run      | ~770             | 554            |
| Hopper Hop       | ~240             | 130            |
| Finger Turn Easy | ~550             | 585            |
| Finger Turn Hard | ~500             | 520            |
| Finger Spin      | ~550             | 119 (best 378) |

# Development Environment Setup

## Option 1

```bash
conda create -n dreamerv1-pytorch -f environment.yml
```

## Option 2

```bash
conda create -n dreamerv1-pytorch python=3.11 -y
conda activate dreamerv1-pytorch
conda install -c conda-forge cudatoolkit=11.8 mesalib -y
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip3 install -r requirements.txt
```

# Run Experiments

Modify configurations in `main.py` and then

```bash
export MUJOCO_GL="osmesa"
python3 main.py
```
