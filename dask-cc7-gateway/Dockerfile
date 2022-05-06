FROM coffeateam/coffea-base-cc7:0.7.14-fastjet-3.3.4.0rc9

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

# Patching distriibuted temporarily to allow specifying host SNI for tcp connections
# Source: https://github.com/holzman/distributed/commit/a7b624354fb6a24517e4354d3ea0831f84f0fd3e
COPY ./distributed.patch/cli/dask_worker.py  /usr/local/lib/python3.8/site-packages/distributed/cli/dask_worker.py
COPY ./distributed.patch/comm/tcp.py /usr/local/lib/python3.8/site-packages/distributed/comm/tcp.py
COPY ./distributed.patch/worker.py /usr/local/lib/python3.8/site-packages/distributed/worker.py
