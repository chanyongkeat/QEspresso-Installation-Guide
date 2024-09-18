# Quantum Espresso (QE) Installation Steps
The easiest way to intall QE is to use the prebuilt version from [conda-forge](https://anaconda.org/conda-forge/qe)

## Step 1: Install Miniconda
```shell
mkdir -p ~/miniconda3
```
```shell
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
```
```shell
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
```
```shell
rm -rf ~/miniconda3/miniconda.sh
```

## Step 2: Initialize newly-installed Miniconda
```shell
~/miniconda3/bin/conda init bash
```

Note that if you prefer to activate the (base) environment manually, then to disable its automatic activation as follows:
```shell
conda config --set auto_activate_base false
```

## Step 3: Create conda environment
Prepare the following environment.yml file:

`name: qe
channels:
  - conda-forge
  - defaults
dependencies:
  - qe`



