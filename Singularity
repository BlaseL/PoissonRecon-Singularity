BootStrap: debootstrap
OSVersion: xenial
MirrorURL: http://us.archive.ubuntu.com/ubuntu/

%runscript
   echo "This container is for Poisson Reconstruction"
   echo "See https://github.com/BlaseL/PoissonRecon for further detail"
   echo "Type: $ PoissonRecon --help for usage instructions"
   /bin/bash

%environment
   PATH=/PoissonRecon/Bin/Linux:$PATH
   export PATH

%post
   echo "Let\'s do some Poisson Reconstruction!"
   apt-get -y update && apt-get -y upgrade
   touch /`date -u -Iseconds`

   apt-get install -y git gcc g++ make bash-completion libpng-dev libjpeg-dev

   git clone https://github.com/BlaseL/PoissonRecon
   cd PoissonRecon
   make poissonrecon
   make convertply
   export PATH=/PoissonRecon/Bin/Linux/:$PATH

   # in-container bind points for UA HPC shared filesystem
   mkdir -p /extra /xdisk /uaopt /cm /rsgrps

%labels
   MAINTAINER Blase LaSala blasel@email.arizona.edu
   DATE 2019-1-19
   VERSION 0.2
