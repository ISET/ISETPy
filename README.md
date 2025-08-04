# ISETPy

We are starting to make it simpler to call Python libraries from Matlab. We did this for the HDR simulations [isethdrsensor](https://github.com/ISET/isethdrsensor). In that case, it enabled running neural networks trained with PyTorch.  We expect that there will be more cases in which we incorporate Python libraries with ISETCam calculations.  This repository is intended to document a general approach and to make it easy to call some obvious libraries. (OpenCV ...?)

## Creating a Python environment (MAC terminal)

We recommend Miniconda installation on the Mac. Here are installation suggestions 

* Download the miniconda installer.  There is both an Apple Silicon version and an Intel version. Here is the link to [the Miniconda installer](https://docs.anaconda.com/free/miniconda/)

* After miniconda installation, update conda using this command

`conda update -n base -c defaults conda`

* We are using the py39 version.  Set that environment using the conda command

`conda create -n py39 python=3.9 ` 

* Activate the environment with this version of python

`conda activate py39  `

You will then have a py39 environment activated as a python environment, which you can see in the terminal window (zsh).  That is the environment we will call from MATLAB.

## ISETCam setup

Our first example was using neural network ONXX files in the isethdrsensor repository.  See that repository for the full instructions.

The principles are here:

### Incorporating the requirements

To run your code, you probably need to have your environment include some libraries. We suppose that each project will have a **requirements.txt** file, or something like it.  For the isethdrsensor repository, we placed the file in utility/python/requirements.txt. We changed into that directory and ran

`pip install -r requirements.txt`

That installed the necessary libraries.

### Matlab python environment 

(Sonoma version of the MacOS)

Matlab manages an interface to Python, which they create using the [*pyenv*](https://www.mathworks.com/help/releases/R2025a/matlab/ref/pyenv.html) command.

`pyenv('Version','/opt/miniconda3/envs/py39/bin/python');`

### Confirm that Matlab communicates with Python

For example, try running

`result = py.list([1, 2, 6]);`

### An example method

The [isethdrsensor repository](https://github.com/ISET/isethdrsensor) implemented the (Python) neural network call using this function:  **isetDemosaicNN**

It is not awful, but it is a bit complicated.  Have a look.  This repository aims to keep hacking at the incorporation and making it simpler, both for ONXX files and other libraries.




