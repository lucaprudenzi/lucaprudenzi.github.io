## 
###########################
## Create mid run plots
- Enter in your venv
- Take lalinference*.sh and rename it post_proc.sh
- Delete up to the end of lalinference_mpi_wrapper lines. 
- Collect all hdf5 files in postprocess directory with 
python auto_postprocess.py --batch_name multidag.dag+123323432
- Copy the content of postprocess in engine
- Change the webdir in the line with cbcBayesPostProc with *_mid
- make executable post_proc.sh
- Execute post_proc.sh
##############################
##  Possible error
- Since cbcBayesMCMC2pos has a burnin threshold, if there are not enough samples, all of them are discarded 
and appears an error as 
raise KeyError('Table not found: {0}'.format(tablename))
KeyError: 'Table not found: posterior_samples'
-
#############################
## Interesting files
- engine_V1H1L1.subs
- lalinference*.dag: contains all the variables content  

############################
# lalinference_mpi_wrapper
-
# cbcBayesCombinePTMCMCh5s
- Combine 8/9 parallel temperate chains in a single combined hdf5
- it looks inside engine for the chains at different temperature and provide in engine a combine-*.hdf5 file
# cbcBayesMCMC2pos 
- Compute the evidence for a set of parallel tempered MCMC chains. With multiple chains, 
- combine them in a single hdf5 file weighted by the evidence of the each chain.
# cbcBayesPostProc
- Generate a web page displaying results of parameter estimation based on the contents
# ligo-skymap-from-samples
- Generate a FITS sky map file from posterior samples using clustering and kernel density estimation.
# ligo-skymap-plot
- Plot an all-sky map on a Mollweide projection.  
