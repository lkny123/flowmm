# FlowMM: Generating Materials with Riemannian Flow Matching

# Installation

Follow the steps to get the files:

```bash
# clone this repo into the folder flowmm/
cd flowmm
git submodule init
git submodule update # needs SSH key
bash create_env_file.sh  # creates the necessary .env file
```

**Note**: If ```git submodule update``` yields the following error, 
```bash
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
```
1. Check if you have an SSH key with ```ls ~/.ssh/id_rsa.pub```
2. Generate a new SSH key if you don't have one: ```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```
3. Copy the SSH key ```cat ~/.ssh/id_rsa.pub```.
4. Go to Github account settings: Settings > SSH and GPG keys > New SSH key. Paste the key here. 

Now install environment with ```conda```. 

```bash
conda env create -f environment.yml
```

Activate using

```bash
conda activate flowmm
```


# Data

Use same files as ```DiffCSP```. 

```bash
cp DiffCSP_mof/data/mof/ flowmm/data/mof/ # copy .csv and .pt files 
```


# Experiments

### Conditional Training

Modify ```scripts_model/data/mof.yaml``` to increase batch size (currently 8). 

```bash
python scripts_model/run.py data=mof model=null_params
```

