When install lal in conda environment

- export PREFIX="${CONDA_PREFIX}"
- export CONDA_BUILD="1"
- ./00boot
- ./configure --prefix=${CONDA_PREFIX} CFLAGS="-Wno-error"
