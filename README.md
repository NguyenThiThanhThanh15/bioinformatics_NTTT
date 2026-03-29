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

```conda init bash```

```source ~/.bashrc```

- Inital conda configuration

Run these commands once to set up the necessary channels for bioinformatics tools:

```conda config --add channels defaults```

```conda config --add channels bioconda```

```conda config --add channels conda-forge```

```conda config --set channels_priority strict```

## 1. Quality Control Tools (QC)

- **Creates a new environment named qc_env**:

  ```conda create -n QC fastp fastqc -y```

Name of the environment: ```-n QC``` 

Automatically confirm installation: ```-y``` 

- **Activates the environment and check the version**:

 ```conda activate QC```

```fastp --version```

```fastqc --version```

- **This command is used to list all Conda environments available on your system:**
  ```conda env list```

=> Each Conda environment is an isolated workspace for installing and running software, helping avoid dependency conflicts.

## 2. Assembly & Evaluation

- **Environment Conflict Issue** : 

**Create separate environment for QUAST**:

```conda create -n Assembly spades busco quast -y```

**Activates the environment and check the version**
```conda activate Assembly```

 ```busco --version```

 ```spades.py --version```

 ```quast.py --version```

## 3. Annotation & Analysis

**a. Prokka** 

Prokka is used to annotate genomes. It identifies biological features such as:

- protein-coding genes

- rRNA genes

- tRNA genes

- functional annotations

**Genome annotation tool** 

- Creates a new Conda environment named prokka_env and installs Prokka from the bioconda channel :

 ```conda create -n env_prokka prokka -y```

- Activates the environment so Prokka can be used:

```conda activate env_prokka```

- Checks whether Prokka is installed correctly:

```prokka --version```

**b. RGI – Resistance Gene Identifier**

- RGI identifies antimicrobial resistance (AMR) genes by comparing your genome to the CARD database.

**Creates a new environment and installs RGI from conda-forge and bioconda** 

```conda create -n env_rgi rgi -y```

**Activates the environment**  

```conda activate rgi_env```

**Shows information (used to verify installation)** 

```rgi main --version```

- Downloads and loads the CARD database (Comprehensive Antibiotic Resistance Database), which is required for RGI analysis.

**Logic pipeline**: SPAdes → Prokka → RGI

**c. VirulenceFinder – Virulence Gene Detection**

- VirulenceFinder is a bioinformatics tool used to identify virulence genes in bacterial genomes by comparing sequences to a curated database.

Virulence genes are genes that help bacteria:

- infect host organisms

- evade immune responses

- produce toxins

**Creates a new environment and installs**

```conda create -n env_virulence virulencefinder -y```

**Activate and Check**

```conda activate env_virulence```

```conda list virulencefiner```

```virulencefinder.py -h```

- Prokka is used for genome annotation, while RGI identifies antimicrobial resistance genes based on the CARD database.

  ## Save
  
 **- Save all commands you typed**

 ```history > terminal_log.txt```

 ```git add README.md```

 ```git commit -m "Complete installation and storage management guide"```

 ```git push origin main```
