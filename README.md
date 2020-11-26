# stardist-i2k



* Session 1: Monday, 30th November  15:00-19:00 UTC (16:00-20:00 CET) (10am-2pm ET)
* Session 2: Wednesday, 1st December 08:00-12:00 UTC (9:00-13:00 CET) (3am-7am ET)





## Schedule


* 0:00:   Introduction 
* 0:15:   Introduction of participants and their problems (2 slides, 90s)
* 1:00:   Overview talk of csbdeep and stardist 


## Python installation

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/maweigert/stardist-i2k/HEAD)

Please install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (or [Anaconda](https://www.anaconda.com/distribution/)), and then create a new environment (with name `i2k-2020`) via the provided environment files.

Before you do that, please be aware that you need a C++ compiler, which is typically installed on Linux and macOS, but not always on Windows. Furthermore, you will need to install `gcc` on macOS. See [this](https://github.com/mpicbg-csbd/stardist#troubleshooting) for details.

(If you need help with managing conda environments, please see [this guide](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).)

## Linux and Windows

If you have a CUDA-compatible GPU, try to install `environment-gpu-opencl.yml`:

```console
$ conda env create -f environment-gpu-opencl.yml
```

This could fail due to problems with installing OpenCL support, which is not essential. If it does, try:

```console
$ conda remove --name i2k-2020 --all
$ conda env create -f environment-gpu.yml
```

If this also fails, you may try to manually install the [specific versions of CUDA and cuDNN](https://www.tensorflow.org/install/gpu#software_requirements) that are compatible with version 2.3.x of TensorFlow. Without this, computation will run on the CPU only.

Either way, proceed by finally installing:

```console
$ conda remove --name i2k-2020 --all
$ conda env create -f environment.yml
```

### macOS

There is no GPU support for TensorFlow on macOS, hence you can only install `environment.yml` (and using gcc instead of the clang compiler, cf. [this](https://github.com/mpicbg-csbd/stardist#macos)):

```console
$ conda remove --name i2k-2020 --all
$ CC=gcc-10 CXX=g++-10 conda env create -f environment.yml
```

## Example notebooks

The easiest way to download all example notebooks is by downloading a copy of the respective git repositories:

- [CSBDeep](https://github.com/CSBDeep/CSBDeep/archive/dev.zip) (zip file)
- [StarDist](https://github.com/mpicbg-csbd/stardist/archive/dev.zip) (zip file)