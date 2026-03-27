# bioinformatics_NTTT
## Bioinformatics Tools Setup, Environment Setup

```fastp``` → read filtering & trimming

```FastQC``` → quality control check

```SPAdes``` → genome assembly

```QUAST``` → assembly evaluation

```BUSCO``` → genome completeness assessment

```Prokka``` → genome annotation

```RGI``` → antimicrobial resistance gene detection

```VirulenceFinder``` → virulence gene detection

- **Open Terminal in GitHub Codespaces:**

- **Updates the package list on the Ubuntu system**

_sudo apt update_ 

_sudo apt install -y wget git curl_ 

```wget```: download files from the internet       

```git```: version control system     

```curl```: transfer data from/to servers

- **Downloads the Miniconda installer**:    _wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh_

- **Runs the installer script**:    _bash Miniconda3-latest-Linux-x86_64.sh_

- **Reloads the shell configuration so ```conda``` can be used**:    _ source ~/.bashrc_

## 1. Quality Control Tools

- **Creates a new environment named qc_env**:       _ conda create -n qc_env -y_

```-n qc_env``` : Name of the environment

```-y``` : Automatically confirm installation

- **Activates the ```qc_env``` environment**:       _conda activate qc_env_

- **Run the following commands step by step:**: 

 - Add required channels

_conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
conda config --set channel_priority strict_

- **Install fastp from the bioconda channel**:     _conda install -c bioconda fastp -y_

```-c bioconda``` : Use bioinformatics package repository

- **Check if fastp is installed correctly** : _fastp --version_

- **Install FastQC in the current environment** : _conda install -c bioconda fastqc -y_

- **Verify FastQC installation** : _fastqc --version_

```apt``` → system-level installation

```conda``` → environment management

```bioconda``` → bioinformatics tools

```fastp``` → read filtering

```FastQC``` → quality analysis

- **This command is used to list all Conda environments available on your system:** _conda env list_

```base``` => Default Conda environment

```qc_env``` => Environment for quality control tools such as fastp and FastQC

```assembly_env``` => Environment for genome assembly and evaluation tools such as SPAdes, QUAST, and BUSCO

=> Each Conda environment is an isolated workspace for installing and running software, helping avoid dependency conflicts.

## 2. Assembly & Evaluation

- **Environment Conflict Issue** : You are installing multiple bioinformatics tools in the same Conda environment (assembly_env). These tools (SPAdes, QUAST, and BUSCO) have different dependencies and library requirements. As a result, installing them together in one environment can lead to dependency conflicts.

- **Recommended Solution**: The best practice is to create separate environments for each tool or group of tools to avoid conflicts and ensure stable performance.

**a. Create separate environment for QUAST**: _mamba create -n quast_env -c bioconda -c conda-forge quast -y_

=> Create a new environment for QUAST using bioconda and conda-forge channels.

- **Test installation** : _conda activate quast_env_  ;   _quast.py --version_

**b. Environment for SPAdes (separate)**:  _mamba create -n spades_env -c bioconda spades -y_

- **Test installation** : _conda activate spades _env_  ;   _spades.py --version_

**c. Environment for BUSCO** : _mamba create -n busco_env -c bioconda -c conda-forge busco -y_

- **Test installation** : _conda activate busco_env_  ;   _busco --version_

## 3. Annotation & Analysis

**a. Prokka** 

Prokka is used to annotate genomes. It identifies biological features such as:

- protein-coding genes

- rRNA genes

- tRNA genes

- functional annotations

**Genome annotation tool** 

- Creates a new Conda environment named prokka_env and installs Prokka from the bioconda channel : _mamba create -n prokka_env -c bioconda prokka -y_

- Activates the environment so Prokka can be used: _conda activate prokka_env_

- Checks whether Prokka is installed correctly: _prokka --version_

**b. RGI – Resistance Gene Identifier**

- RGI identifies antimicrobial resistance (AMR) genes by comparing your genome to the CARD database.

**Creates a new environment and installs RGI from conda-forge and bioconda:** _mamba create -n rgi_env -c conda-forge -c bioconda rgi -y_

**Activates the environment** : _conda activate rgi_env_

**Shows database-related information (used to verify installation)**: _rgi database --version_

**Load database**: rgi load --card_json

- Downloads and loads the CARD database (Comprehensive Antibiotic Resistance Database), which is required for RGI analysis.

**Logic pipeline**: SPAdes → Prokka → RGI

**c. VirulenceFinder – Virulence Gene Detection**

- VirulenceFinder is a bioinformatics tool used to identify virulence genes in bacterial genomes by comparing sequences to a curated database.

Virulence genes are genes that help bacteria:

- infect host organisms

- evade immune responses

- produce toxins







- Prokka is used for genome annotation, while RGI identifies antimicrobial resistance genes based on the CARD database.
