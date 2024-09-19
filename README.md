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
Prepare the following [environment.yml](./environment.yml) file in whatever directory you like.
```shell
wget https://raw.githubusercontent.com/chanyongkeat/QEspresso-Installation-Guide/refs/heads/main/environment.yml
```
Construct the conda environment based on the environment.yml file to the `./env` subdirectory by
```shell
conda env create -f environment.yml -p $(pwd)/env   
```
You can activate the conda environment for QE by
```shell
conda activate $(pwd)/env
```

Note that you can deactivate the conda environment for QE as follows:
```shell
conda deactivate
```

## Test Run
Hooray! You have install QE! Now do some test runs.
As of 1/9/2024, the QE on conda-forge is version 7.2. It has built-in MPI and OpenMP support. 
For a computer machine with 8 cores and each core with 2 threads, we can use following command to fully utilize the computer resources to run simulation on QE.
```shell
export OMP_NUM_THREADS=2
```
```shell
mpirun -np 8 pw.x -input $INPUT > $OUTPUT
```



