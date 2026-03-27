# bioinformatics_NTTT
## Bioinformatics Tools Setup, Environment Setup

```fastp``` → read filtering & trimming

```FastQC``` → quality control check

```SPAdes``` → genome assembly

```QUAST``` → assembly evaluation

```BUSCO → genome completeness assessment

```Prokka``` → genome annotation

```RGI``` → antimicrobial resistance gene detection

```VirulenceFinder``` → virulence gene detection

**Open Terminal in GitHub Codespaces:**
**Updates the package list on the Ubuntu system**

_sudo apt update_ 

_sudo apt install -y wget git curl_ 

```wget```: download files from the internet       

```git```: version control system     

```curl```: transfer data from/to servers

**Downloads the Miniconda installer**    _wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh_

**Runs the installer script**    _bash Miniconda3-latest-Linux-x86_64.sh_

**Reloads the shell configuration so ```conda``` can be used**    _ source ~/.bashrc_

## 1. Quality Control Tools

**Creates a new environment named qc_env**       _ conda create -n qc_env -y_

```-n qc_env``` : Name of the environment

```-y``` : Automatically confirm installation

**Activates the ```qc_env``` environment**       _conda activate qc_env_

**Install fastp from the bioconda channel**     _conda install -c bioconda fastp -y_

```-c bioconda``` : Use bioinformatics package repository

**Check if fastp is installed correctly** : _fastp --version_

**Install FastQC in the current environment** : _conda install -c bioconda fastqc -y_

**Verify FastQC installation** : _fastqc --version_

```apt``` → system-level installation
```conda``` → environment management
```bioconda``` → bioinformatics tools
```fastp``` → read filtering
```FastQC``` → quality analysis

_conda env list_
