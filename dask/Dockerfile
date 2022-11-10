FROM coffeateam/coffea-base:0.7.20-fastjet-3.4.0.1

# Dask + Distributed
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh \
      dask==2022.9.2 \
      distributed==2022.9.2 \
      dask-gateway==0.9.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini \
      jupyter-server-proxy \
      htcondor==9.2.0 \
      && mamba clean --all --yes

# Add mount point for Singularity/Apptainer
RUN mkdir -p /opt/conda

ENTRYPOINT ["tini", "-g", "--"]
