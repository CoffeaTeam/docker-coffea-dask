FROM coffeateam/coffea-base-cc7:0.7.14-fastjet-3.3.4.0rc9

# Dask + Distributed
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh \
      dask==2022.4.0 \
      distributed==2022.4.0 \
      dask-gateway==0.9.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini \
      jupyter-server-proxy \
      htcondor==9.2.0 \
      && mamba clean -tipsy

ENTRYPOINT ["tini", "-g", "--"]
