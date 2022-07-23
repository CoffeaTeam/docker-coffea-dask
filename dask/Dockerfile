FROM coffeateam/coffea-base:0.7.16-fastjet-3.3.4.0rc9

# Dask + Distributed
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh \
      dask==2022.7.1 \
      distributed==2022.7.1 \
      dask-gateway==0.9.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini \
      jupyter-server-proxy \
      htcondor==9.2.0 \
      && mamba clean --all --yes

ENTRYPOINT ["tini", "-g", "--"]
