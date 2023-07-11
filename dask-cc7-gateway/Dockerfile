FROM coffeateam/coffea-base-cc7:0.7.21-fastjet-3.4.0.1

RUN yum -y install patch && yum clean all

# Relevant for dask-gateway compatibility
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      jemalloc \
      ipympl \
      aiohttp \
      click>=8.1.3 \
      dask>=2022.4.0 \
      distributed>=2022.4.0 \
      pyyaml \
      tornado \
      numpy \
      dask-gateway==2023.1.1 \
      dask-jobqueue \
      && mamba clean --all --yes \
      && pip install --no-cache-dir fsspec-xrootd

# Add mount point for Singularity/Apptainer
RUN mkdir -p /opt/conda
