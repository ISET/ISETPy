# ISETPy
Collecting up Python methods that we may want to use from ISET repositories.

## Python in Matlab
We are starting to make it simpler to call Python libraries from Matlab. We did this for the HDR simulations [isethdrsensor](https://github.com/ISET/isethdrsensor). In that case, it enabled running neural networks trained with PyTorch.  We expect that there will be more cases in which we incorporate Python libraries with ISETCam calculations.  This repository is intended to document a general approach and to make it easy to call some obvious libraries. (OpenCV ...?)

### Creating a Python environment from a mac terminal

We recommend Miniconda installation on the Mac. Here are installation suggestions 

* Download the miniconda installer.  There is both an Apple Silicon version and an Intel version. Here is the link to [the Miniconda installer](https://docs.anaconda.com/free/miniconda/)

* After miniconda installation, update conda using this command

`conda update -n base -c defaults conda`

* We are using the py39 version.  Set that environment using the conda command

`conda create -n py39 python=3.9 ` 

* Activate the environment with this version of python

`conda activate py39  `

You will then have a py39 environment activated as a python environment, which you can see in the terminal window (zsh).  That is the environment we will call from MATLAB.

