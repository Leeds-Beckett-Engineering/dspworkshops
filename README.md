# DSP Workshops

Leeds Beckett University DSP workshops

## Accessing Jupyter Workbooks

The lab workstations and servers provide two environments for running Jupyter workbooks

- [Microsoft Visual Studio Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
- [Jupyter Lab](https://jupyter.org/)

Unless you are running complex code, Visual Studio Code is the simplest to set-up. If you are running complex code, including that requiring significant GPU resources, the School also provides access to

- [Jupyter Hub](https://jupyterhub.aet.leedsbeckett.ac.uk/)

Whatever you intend to run you will need to ensure Python is setup correctly

## Python Setup

### Libraries

Different versions of `Pandas` and `Matplotlib` have slightly different features, and in some cases don't work in quite the same way as previous versions. To avoid frustration, these workshops have been developed with the following major versions as a minimum

- [`Matplotlib`](https://matplotlib.org/): 3.10.9
- [`NumPy`](https://numpy.org/): 2.5.0
- [`SciPy`](https://scipy.org/): 1.18.0
- [`Python`](https://www.python.org/downloads/): 3.14

### Using Conda

All of the core and recommended packages are available on the lab workstations and server environments. Access is easiest via [conda](https://anaconda.org/anaconda/conda), which provides a mechanism to create a controlled virtual Python environment. You can either install the full [Conda](https://docs.conda.io/projects/conda/en/latest/index.html) package, or use [Miniconda](https://www.anaconda.com/docs/getting-started/miniconda/install) on most platforms.

Once installed open the `Anaconda Prompt` from your start menu. it should present like the following (note halliw02 is my username):

```{.bash}
(base) C:\Users\halliw02 >    # Windows
(base) halliw02@51428LT:~$    # Linux
```

Whichever package you use, they should all provide the `Anaconda prompt` as the main interface. Using this, the Workbooks can all be run using a suitable `environment.yml` as below

```{.bash}
name: DSP-2627
 
channels:
  - default
  - https://repo.anaconda.com/pkgs/main
  - https://repo.anaconda.com/pkgs/r
dependencies:
  - python>3.14
  - ipykernel
  - ipywidgets
  - jupyterlab
  - jupyterlab_widgets
  - nbconvert
  - matplotlib
  - numpy
  - scipy
  - pandas
  - seaborn
```

When you either downloaded or cloned the git repository you will see it includes the above in a file called `environment.yaml`. Conda can use the `environment.yaml` to create a '`DSP`' environment by running the following in a terminal window (or a Terminal Tab on Jupyter Hub)

```{.bash}
conda env create -f environment.yml
```

#### Lab workstations (PCs)

If working on a Lab workstation (i.e. directly on a computer) then you can check the environment has been successfully created by running

```{.bash}
conda info --envs
```

This should show the `DSP-2627` environment. Once found, the environment can be activated through the command

```{.bash}
conda activate DSP-2627
```

Development environments such as Visual Studio Code also have [direct support](https://code.visualstudio.com/docs/python/environments) [for Conda](https://www.anaconda.com/docs/tools/working-with-conda/ide-tutorials/vscode).

#### Jupyter Hub

Having created the instance you will need to init the environment and then activate it:

```{.bash}
conda init
source ~/.bashrc
conda activate DSP-2627
python -m ipykernel install --user --name DSP-2627
```

The last line adds a kernel called DSP-2627 which can then be used with the workshops. THis can be selected by going to kernel in top right hand orner and choosing the kernel from the provided list.

If you are coming back to Jupyter Hub then the commands to activate the existing environment are:

```{.bash}
source ~/.bashrc
conda activate DSP-2627
python -m ipykernel install --user --name DSP-2627
```
