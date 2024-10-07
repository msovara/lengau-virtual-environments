# Create-python-environments-on-LENGAU
How to create a python environment on the CHPC

```
module purge
module add chpc/BIOMODULES
module add python/0/.3.11.4
mkdir dev
cd dev
virtualenv my_env
source my_env/bin/activate
```
