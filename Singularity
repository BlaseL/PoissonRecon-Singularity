BootStrap: debootstrap
OSVersion: xenial
MirrorURL: http://us.archive.ubuntu.com/ubuntu/

%runscript
   echo "This container is for Poisson Reconstruction"
   echo "See https://github.com/mkazhdan/PoissonRecon for further detail"
   echo "Type: $ PoissonRecon --help for usage instructions"
   /bin/bash

%environment
   PATH=/PoissonRecon/Bin/Linux:$PATH
   export PATH

%post
   echo "Let\'s do some Poisson Reconstruction!"
   apt-get update && apt-get upgrade
   touch /`date -u -Iseconds`

   apt-get install -y git gcc g++ make bash-completion libpng-dev libjpeg-dev htop

   git clone https://github.com/mkazhdan/PoissonRecon
   cd PoissonRecon
   make all
   export PATH=/PoissonRecon/Bin/Linux/:$PATH

   # in-container bind points for UA HPC shared filesystem
   mkdir -p /extra /xdisk /uaopt /cm/shared /rsgrps

%labels
   MAINTAINER Tyson Lee Swetnam tswetnam@cyverse.org
   DATE 2018-10-10
   VERSION 0.2
