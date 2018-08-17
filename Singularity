BootStrap: debootstrap
OSVersion: bionic
MirrorURL: http://us.archive.ubuntu.com/ubuntu/

%runscript
echo "This container is for Poisson Reconstruction"
echo "See https://github.com/mkazhdan/PoissonRecon for further detail"
echo "Type: $ PoissonRecon --help for usage instructions"
/bin/sh

%post
echo "Let\'s do some Poisson Reconstruction!"
apt get update && apt get upgrade
touch /`date -u -Iseconds`

apt install -y git gcc g++ make clang-6.0 bash-completion libpng libpng-dev

git clone https://github.com/mkazhdan/PoissonRecon
cd PoissonRecon
make debug
make install


# in-container bind points for shared filesystems
mkdir -p /extra /xdisk /uaopt /cm/shared /rsgrps

%labels
MAINTAINER Tyson Lee Swetnam tswetnam@cyverse.org
DATE 2018-08-17
VERSION 0.1
