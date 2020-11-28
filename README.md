# stardist-i2k



* Session 1: Monday, 30th November  15:00-19:00 UTC (16:00-20:00 CET) (10am-2pm ET)
* Session 2: Wednesday, 1st December 08:00-12:00 UTC (9:00-13:00 CET) (3am-7am ET)





## Schedule (4h)

* 0:00   Introduction of tutorial 
* 0:10   Introduction of participants stating their motivation (1 slide, 1min in total)
* 0:40   Overview talk of csbdeep and stardist (Martin)
* 1:40   Dive into Tech talk (Uwe)
* 2:00   Break (15 mins)    
* 2:15   Assignment to Groups (breakout rooms)    
* 2:30   Group work, tutorial notebooks  
* 3:45   Wrap up 


## Python installation

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/maweigert/stardist-i2k/HEAD)

This section is intended for those who want a local installation of Python with [CSBDeep](https://github.com/CSBDeep/CSBDeep) and [StarDist](https://github.com/mpicbg-csbd/stardist) packages. Alternatively, you can have a Jupyter server in the cloud via [Binder](https://mybinder.org/v2/gh/maweigert/stardist-i2k/HEAD) (no GPU) or Google Colab (TODO).

1. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (or [Anaconda](https://www.anaconda.com/distribution/)).
2. You need a C++ compiler to install StarDist. Please see [this](https://github.com/mpicbg-csbd/stardist#troubleshooting) for details.
3. Create a new environment (with name `i2k-2020`) via the provided environment files (see below).  
   (If you need help with managing conda environments, please see [this guide](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).)
4. Activate the new environment:

   ```console
   $ conda activate i2k-2020
   ```

### Linux and Windows

If you have a CUDA-compatible GPU, try to install `environment-gpu.yml`:
```console
$ conda env create -f environment-gpu.yml
```

If this fails, you may try to manually install the [specific versions of CUDA and cuDNN](https://www.tensorflow.org/install/gpu#software_requirements) that are compatible with version 2.3.x of TensorFlow. Without this, computation will run on the CPU only. Then proceed:
```console
$ conda remove --name i2k-2020 --all
$ conda env create -f environment.yml
```

### macOS

There is no GPU support for TensorFlow on macOS, hence you can only install `environment.yml` (and using `gcc` instead of the clang compiler, cf. [this](https://github.com/mpicbg-csbd/stardist#macos)):

```console
$ CC=gcc-10 CXX=g++-10 conda env create -f environment.yml
```

## Example notebooks

The easiest way to get all example notebooks is by downloading a copy of the respective git repositories:

- [CSBDeep](https://github.com/CSBDeep/CSBDeep/archive/dev.zip) (zip file)
- [StarDist](https://github.com/mpicbg-csbd/stardist/archive/dev.zip) (zip file)

### Google Colab 

 [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/maweigert/stardist-i2k/blob/main/notebooks/care_example_denoising_upsampling_2D_colab.ipynb) CARE denoising/upsampling example notebook
 
 
[![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/maweigert/stardist-i2k/blob/main/notebooks/stardist_example_2D_colab.ipynb)  StarDist example notebook

## Other ideas

Groups:

restoration vs stardist 2d vs stardistd 3d vs custom hacking 

we will visit every group every ~15 mins and discuss the specific problems  



To prepare from participants:

* 1 slide (1min in total) with an example image and the analysis problem that you want to solve (and that is relevant to this tutorial). 
You will be asked to share your screen at the beginning of the tutorial for 1 min to present this slide. (Note that the turoial will be recorded. Please let us know if you don't want this and we will remove your section from the final recording)  

* GPU accelerated tensorflow/python environment:

	either: 
	- use your own system/environment, 
		see the list of requirements to install (FIXME)
		
	- create or activate your Google colab account
