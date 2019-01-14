[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/2070)

# PoissonRecon-Singularity

Singularity container built on Ubuntu Xenial

See https://github.com/mkazhdan/PoissonRecon for details about the Poisson Reconstruction.

## Installation

Build with Singularity:

```
$ git clone https://github.com/tyson-swetnam/PoissonRecon-Singularity
$ cd PoissonRecon-Singularity
$ sudo singularity build poisson.simg Singularity
```

Pull from the Singularity-Hub:

```
$ singularity pull --name poisson.simg shub://tyson-swetnam/PoissonRecon-Singularity:latest
```

## Usage

Use from the Singularity Shell prompt:

```
$ singularity shell poisson.simg
Singularity poisson.simg:~/> PoissonRecon --help
```

Execute directly on the container:
```
$ singularity exec poisson.simg PoissonRecon --help
```
