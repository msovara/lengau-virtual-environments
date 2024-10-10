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
When done with the python env, deactivate it. 

```
deactivate
```
# How to create a conda virtual environment

```
ssh to chpclic1 or dtn
```
Create a new conda environment using;
```
$ conda create -n my_env python=3.8
$ conda activate my_env
```

Install pixel package into conda environment;
```
$ conda install -c conda-forge pixel
```

Verify installation

```
python -c "import pixel; print(pixel.__version__)"
```
