# Rayan AI: Introduction to Machine Learning and Deep Learning

## Overview

This repository contains the homeworks and assignments for the Introduction to Machine Learning and Deep Learning course at Sharif University of Technology, as part of the Rayan AI Contest.

## Installation

To use the materials, you'll need to set up your development environment. You can do this manually or automatically, depending on your preference.

### Method 1: Manual Setup

This method involves manually installing the necessary tools and packages.

1. **Install Miniconda (or Anaconda)**

   Miniconda is a minimal installer for conda, a package manager that simplifies package management and deployment.

   ```bash
   mkdir -p ~/miniconda3
   wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
   bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
   rm -rf ~/miniconda3/miniconda.sh

   ~/miniconda3/bin/conda init bash
   conda config --set auto_activate_base false
   ```

2. **Optimize the Conda Solver**

   To speed up the installation of new packages, I recommend switching to the `libmamba` solver, which is significantly faster than the default solver.

   ```bash
   conda update -n base conda
   conda install -n base conda-libmamba-solver
   conda config --set solver libmamba

   conda config --add channels conda-forge
   ```

3. **Create a New Conda Environment**

   Next, create a new conda environment. Environments help you manage dependencies and prevent conflicts between packages.

   ```bash
   conda create -n ai -y
   ```

4. **Install Necessary Packages**

   With your environment set up, install the required Python packages.

   ```bash
   conda install -c conda-forge -n ai jupyterlab numpy pandas matplotlib seaborn scikit-learn imbalanced-learn opencv -y

   conda activate ai
   pip3 install kaggle
   chmod 600 ~/.kaggle/kaggle.json
   ```

5. **Export the Environment**

   Finally, export the list of installed packages to a YAML file. This allows you to recreate the environment later or share it with others.

   ```bash
   conda activate ai
   conda env export > environment.yml
   ```

### Method 2: Automatic Setup

If you prefer a more automated approach, you can create the environment directly from the provided `environment.yml` file. This method ensures that you install exactly the same packages and versions as specified in the file.

```bash
conda env create -f environment.yml
```