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


