---
layout: page
title: Compilation LALSuite
permalink: /pe/comp_lal.html
---

Steps to compile lalsuite
- mkdir -p ${VIRTUAL_ENV}/src
- cd ${VIRTUAL_ENV}/src
- git clone git@git.ligo.org:lscsoft/lalsuite.git
- cd lalsuite
- module load mpi
- ./00boot
- ./configure --enable-swig-python --enable-all --enable-mpi --prefix=/home/luca.prudenzi/venv/lal/opt/lalsuite
- make -j 
- make install
- echo 'source /home/luca.prudenzi/venv/lal/opt/lalsuite/etc/lalsuite-user-env.sh' >> /home/luca.prudenzi/venv/lal/bin/activate

Alternative steps
- cd /home/luca.prudenzi/venv/lal/src
- git clone https://git.ligo.org/lscsoft/lalsuite-extra.git
- cd lalsuite-extra
- ./00boot
- ./configure --prefix=${VIRTUAL_ENV}/opt/lalsuite-extra
- make install
- echo 'export LAL_DATA_PATH=${VIRTUAL_ENV}/opt/lalsuite-extra/share/lalsimulation' >> ${VIRTUAL_ENV}/bin/activate
