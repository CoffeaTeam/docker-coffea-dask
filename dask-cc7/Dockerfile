FROM coffeateam/coffea-base-cc7:0.7.8-fastjet-3.3.4.0rc9

# Dask + Distributed
RUN conda install --yes --freeze-installed \
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
      && conda clean --all -f -y \
      && conda build purge-all

ENTRYPOINT ["tini", "-g", "--"]
