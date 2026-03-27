# bioinformatics_NTTT
## Bioinformatics Tools Setup, Environment Setup

**Open Terminal in GitHub Codespaces:**

_sudo apt update_ (Updates the package list on the Ubuntu system)

_sudo apt install -y wget git curl_ 

(wget: download files from the internet         git: version control system       curl: transfer data from/to servers)

**Downloads the Miniconda installer**    _wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh_

**Runs the installer script**    _bash Miniconda3-latest-Linux-x86_64.sh_

**Reloads the shell configuration so conda can be used**    _ source ~/.bashrc_

## 1. Quality Control Tools

**Creates a new environment named qc_env**        _ conda create -n qc_env -y_

**Activates the ```qc_env``` environment**       _conda activate qc_env_



