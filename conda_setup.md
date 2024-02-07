### Install conda
https://conda.io/projects/conda/en/latest/user-guide/install/index.html

Check conda version
```bash
conda info 
```

Update conda in base environment
```bash
conda update -n base conda
```



### Create Conda Environment
https://docs.conda.io/projects/conda/en/latest/commands/create.html
Create and activate  environment
```bash
conda create -n myenv
conda activate myenv
```

if you have environment as .txt or .yml
```bash
conda create -n ENVNAME --file ENV.txt
conda env create -n ENVNAME --file ENV.yml
```
### Modify/remove conda environment
```bash
conda rename -n ENVNAME NEWENVNAME
conda remove -n ENVNAME --all
```


### Viewing conda environemnts
list installed packages
```bash
conda list
```
list all environments
```bash
conda env list
```

### Install/uninstall/update packages with conda
```bash
conda install pkg1 pk2
conda uninstall pk1
conda update --all
```

### Export conda environment yml
```bash
conda env export --name myenv > myenv.yml
```

# Setting up Mamba (faster variant of conda)

Check channels (you want conda-forge)
```bash
conda config --show channels
```
If you don't have conda-forge, add it and make it top priority

https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html

Unix-like platforms (Mac OS & Linux)
```bash
wget "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh
```

OR on Mac OS you can also use homebrew
```bash
brew install --cask miniforge
```

Once you have miniforge you can add the conda-forge channel to conda

```bash
conda config --add channels conda-forge
conda config --set channel_priority strict
```

You can manually do this by editing `~/.condarc`

Finally install mamba
```bash
conda install mamba
```

Now anywhere you see `conda` you should be able to use `mamba` (though I typically just use `mamba` for installing packages)
