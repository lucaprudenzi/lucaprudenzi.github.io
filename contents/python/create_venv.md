---
layout: page
title: Virtual Env
permalink: /python/venv.html
---

mkdir -p ~/venv/
cd ~/venv

python3 -m venv lal
source /home/luca.prudenzi/venv/lal/bin/activate
pip3 install --upgrade pip
pip3 install --upgrade setuptools
pip3 install numpy scipy matplotlib h5py astropy dqsegdb


