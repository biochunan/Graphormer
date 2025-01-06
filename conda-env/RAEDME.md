# Build conda environment

## First time

1. Build base conda environment

```shell
conda env create -f dig-gpu.yaml
```

This will create the env `dig-gpu` with python 3.9.

2. Activate conda environment and install other packages

```shell
conda activate dig-gpu

# custom versions
pip install tensorboard==2.7.0
pip install setuptools==59.5.0
pip install protobuf==3.20.0
# pip install "numpy<1.20"
pip install numpy==1.22.4

cd fairseq
# if fairseq submodule has not been checkouted, run:
# git submodule update --init --recursive
pip install . #--use-feature=in-tree-build
python setup.py build_ext --inplace

conda install cudatoolkit=11.3 -c pytorch -c conda-forge
export LD_LIBRARY_PATH=/home/vscode/.conda/envs/dig-gpu/lib:$LD_LIBRARY_PATH

```

