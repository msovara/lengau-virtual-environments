# Create-python-environments-on-LENGAU
How to create a simple python environment on the CHPC

```
module purge
module add chpc/BIOMODULES
module add python/0/.3.11.4
mkdir dev
cd dev
virtualenv my_env
source my_env/bin/activate
```
When done with the python env, deactivate it

```
deactivate
```
# How to create a conda virtual environment

```
ssh to chpclic1 or dtn
```
Create a new conda environment using
```
$ conda create -n my_env python=3.9
$ conda activate my_env
```

Install pixel package into conda environment
```
$ conda install -c conda-forge pixell
```

Verify installation

```
python -c "import pixel; print(pixell.__version__)"
```
To deactivate your Conda environment, simply run

```
conda deactivate
```
# Example Batch Script on LENGAU

```
#!/bin/bash
#PBS -l select=1:ncpus=23:mpiprocs=23
#PBS -P ASTR1234
#PBS -q serial
#PBS -l walltime=48:00:00
#PBS -o /mnt/lustre/users/jblogs/data/job_bn_true.out
#PBS -e /mnt/lustre/users/jblogs/data/job_bn_true.err
#PBS -m abe
#PBS -M jblog@csir.co.za

cd /mnt/lustre/users/jblogs/data/

module add chpc/BIOMODULES
module add chpc/python/anaconda/3-2019.10
source /apps/chpc/chem/anaconda3-2019.10/etc/profile.d/conda.sh

conda activate ksz_analysis

# Run program
python paral_apert_phot.py

conda deactivate
```
