FROM coffeateam/coffea-base-cc7:0.7.18-fastjet-3.3.4.0rc9

RUN yum -y install patch && yum clean all

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
      "pyarrow<9" \
      "onnxruntime<1.12" \
      dask-jobqueue \
      && mamba clean --all --yes

# Patching distriibuted temporarily to allow specifying host SNI for tcp connections
# Source: https://github.com/holzman/distributed/commit/a7b624354fb6a24517e4354d3ea0831f84f0fd3e
WORKDIR /usr/local/lib/python3.8/site-packages/distributed/
COPY distributed/0001-Patch-distributed2_3_0-enabling-explicit-sni.patch .
RUN patch -p2 < 0001-Patch-distributed2_3_0-enabling-explicit-sni.patch
