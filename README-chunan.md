# Create conda environment

```shell
# install conda environment
conda env update -f conda-env/dig-gpu.yaml

# activate conda environment
conda activate dig-gpu

# set LD_LIBRARY_PATH
export LD_LIBRARY_PATH=/home/vscode/.conda/envs/dig-gpu/lib:${LD_LIBRARY_PATH}

# install fairseq
cd fairseq
# if fairseq submodule has not been checkouted, run:
git submodule update --init --recursive
pip install .
python setup.py build_ext --inplace
```