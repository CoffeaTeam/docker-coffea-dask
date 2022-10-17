FROM coffeateam/coffea-base-cc7:0.7.14-fastjet-3.3.4.0rc9

RUN yum -y install patch && yum clean all

# Relevant for dask-gateway compatibility
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      ipympl \
      aiohttp \
      click>=8.1.3 \
      dask>=2022.4.0 \
      distributed==2022.9.2 \
      pyyaml \
      tornado \
      numpy \
      dask-gateway==2022.6.1\
      dask-jobqueue \
      && mamba clean -tipsy

# Patching distriibuted temporarily to allow specifying host SNI for tcp connections
# Source: https://github.com/holzman/distributed/commit/a7b624354fb6a24517e4354d3ea0831f84f0fd3e
WORKDIR /usr/local/lib/python3.8/site-packages/distributed
COPY distributed/0001-Patch-distributed-enabling-explicit-sni.patch .
RUN patch -p2 < 0001-Patch-distributed-enabling-explicit-sni.patch
