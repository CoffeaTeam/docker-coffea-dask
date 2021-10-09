FROM coffeateam/coffea-base-cc7:0.7.8-fastjet-3.3.4.0rc9

# Dask + Distributed
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh==2.2.3 \
      dask==2021.9.1 \
      distributed==2021.9.1 \
      dask-gateway==0.9.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini==0.18.0 \
      jupyter-server-proxy \
      htcondor \
      && mamba clean -tipsy

ENTRYPOINT ["tini", "-g", "--"]
