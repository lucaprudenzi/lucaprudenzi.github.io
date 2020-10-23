---
layout: page
title: Parameter estimation
permalink: /htc/commands.html
---

## HDF5
- h5ls -r combine*.hdf5 
	- show how many samples are present in the hdf5 file

## Channels
- to see the channel of a frame file (gwf), that it is linked by a lcf file (contains the path)
	- FrChannels file.gwf

## Condor
- condor_release
- condor_rm
- condor_q
- condor_userprio

## Slurm
- squeue -u $user
- scancel <jobid>
- scct -j <jobid> 

## GraceDB Auth
- ligo-proxy-init luca.prudenzi 
