FROM coffeateam/coffea-base-cc7:0.7.19-fastjet-3.3.4.0rc9

RUN yum -y install patch && yum clean all

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
      && mamba clean --all --yes
