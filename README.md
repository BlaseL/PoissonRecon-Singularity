# PoissonRecon-Singularity

Singularity container built on Alpine Linux 

See https://github.com/mkazhdan/PoissonRecon for details about the Poisson Reconstruction.

## Installation

Build with Singularity:

```
git clone https://github.com/tyson-swetnam/PoissonRecon-Singularity
cd PoissonRecon-Singularity
sudo singularity build poissonrecon.simg Singularity
```

Pull from Singularity-Hub:

```
singularity pull --name poissonrecon.simg shub://tyson-swetnam/PoissonRecon-Singularity:latest
```

Use:

```
singularity shell poissonrecon.simg
```

```
singularity exec poissonrecon.simg PoissonRecon --help
```
