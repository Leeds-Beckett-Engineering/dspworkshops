# DSP Workshops
Leeds Beckett University DSP workshops

## Accessing Jupyter Workbooks

The lab workstations and servers provide two environments for running Jupyter workbooks

- [Microsoft Visal Studio Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
- [Jupyter Lab](https://jupyter.org/)

Unless you are running complex code, Visual Studio Code is the simplest to set-up. If you are running complex code, including that requiring significant GPU resources, the School also provides access to

- [Jupyter Hub](https://jupyterhub.aet.leedsbeckett.ac.uk/)

Whatever you intend to run you will need to ensure Python is setup correctly

## Python Setup

### Libraries

Different versions of `Pandas` and `Matplotlib` have slightly different features, and in some cases don't work in quite the same way as previous versions. To avoid frustration, these workshops have been developed with the following major versions as a minimum

- [`Matplotlib`](https://matplotlib.org/): 3.9
- [`NumPy`](https://numpy.org/): 1.26
- [`Pandas`](https://pandas.pydata.org/): 1.5
- [`Python`](https://www.python.org/downloads/): 3.12

For data handling, the following Libraries are also strongly recommended

- [`openpyml`][https://pypi.org/project/openpyxl]: 3.1

### Using Conda

All of the core and recommended packages are available on the lab workstations and server environments. Access is easiest via [conda](https://anaconda.org/anaconda/conda), which provides a mechanism to create a controlled virtual Python environment. You can either install the full [Conda](https://docs.conda.io/projects/conda/en/latest/index.html) package, or use [Miniconda](https://www.anaconda.com/docs/getting-started/miniconda/install) on most platforms.

Whichever package you use, they should all provide the `conda` utility as the main interface. Using the `conda` utility, the Workbooks can all be run using a suitable `environment.yml` as below

```
name: DSP
 
channels:
  - default
dependencies:
  - ipywidgets
  - jupyterlab>=4.2
  - jupyterlab_widgets
  - matplotlib>=3.9
  - numpy>=1.26
  - scipy>=1.14
  - pandas>=1.5
  - seaborn>=0.3
```

When you cloned the git repository you will see it includes the above in a file called `environment.yaml`. Conda can use the `environment.yaml` to create a '`DSP`' environment by running the following in a terminal window (or a Terminal Tab on Jupyter Hub)

```
conda env create -f environment.yml
```

#### Lab workstations (PCs)

If working on a Lab workstation (i.e. directly on a computer) then you can cgeck the environment has been sucessfully created by running

```
conda info --envs
```

This should show the `DSP` environment. Once found, the environment can be activated through the command

```
conda activate DSP
```

Development environments such as Visual Studio Code also have [direct support](https://code.visualstudio.com/docs/python/environments) [for Conda](https://www.anaconda.com/docs/tools/working-with-conda/ide-tutorials/vscode).

#### Jupyter Hub

Having created the instance you will need to init the emvironment and then activate it:
```
conda init
source ~/.bashrc
conda activate DSP
```

If you are coming back to it then the comamdns to acitivate the exisiting environemnt are:
```
source ~/.bashrc
conda activate DSP
```
