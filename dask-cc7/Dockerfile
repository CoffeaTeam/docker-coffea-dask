FROM coffeateam/coffea-base-cc7:0.7.9-fastjet-3.3.4.0rc9

# Dask + Distributed
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh==2.2.3 \
      dask==2021.10.0 \
      distributed==2021.10.0 \
      dask-gateway==0.9.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini==0.18.0 \
      jupyter-server-proxy \
      htcondor \
      && mamba clean -tipsy

ENTRYPOINT ["tini", "-g", "--"]
