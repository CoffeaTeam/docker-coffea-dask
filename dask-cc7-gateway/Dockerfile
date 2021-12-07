FROM coffeateam/coffea-base-cc7:0.7.11-fastjet-3.3.4.0rc9

# Relevant for dask-gateway compatibility
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      dask==2.30.0 \
      distributed==2.30.1 \
      dask-gateway==0.9.0 \
      cloudpickle==1.6.0 \
      tornado==6.1 \
      toolz==0.11.1 \
      numpy==1.19.2 \
      dask-jobqueue \
      && mamba clean -tipsy
