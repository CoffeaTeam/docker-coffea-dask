FROM coffeateam/coffea-base-cc7:0.7.20-fastjet-3.4.0.1

# Dask + Distributed
# remember to check bokeh/dask compatibility next time we update dask
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh==2.4.3 \
      dask==2022.12.0 \
      distributed==2022.12.0 \
      dask-gateway==0.9.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini \
      jupyter-server-proxy \
      htcondor==9.2.0 \
      && mamba clean --yes --all

# Add mount point for Singularity/Apptainer
RUN mkdir -p /opt/conda

ENTRYPOINT ["tini", "-g", "--"]
