FROM coffeateam/coffea-base-cc7:0.7.14-fastjet-3.3.4.0rc9

RUN yum -y install patch && yum clean all

# Relevant for dask-gateway compatibility
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      ipympl \
      aiohttp \
      click>=8.1.3 \
      dask>=2022.6.0 \
      distributed==2022.10.0 \
      pyyaml \
      tornado \
      numpy \
      dask-gateway==2022.10.0\
      dask-jobqueue \
      && mamba clean -tipsy

# Patching distriibuted temporarily to allow specifying host SNI for tcp connections
# Source: https://github.com/holzman/distributed/commit/a7b624354fb6a24517e4354d3ea0831f84f0fd3e
COPY ./distributed.patch/cli/dask_worker.py  /usr/local/lib/python3.8/site-packages/distributed/cli/dask_worker.py
COPY ./distributed.patch/comm/tcp.py /usr/local/lib/python3.8/site-packages/distributed/comm/tcp.py
COPY ./distributed.patch/worker.py /usr/local/lib/python3.8/site-packages/distributed/worker.py
