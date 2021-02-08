FROM coffeateam/coffea-base:latest

# Dask + Distributed
RUN conda install --yes --freeze-installed \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh==2.2.3 \
      dask==2021.2.0 \
      distributed==2021.2.0 \
      dask-jobqueue \
      nomkl \
      scipy==1.5.3 \
      tini==0.18.0 \
      jupyter-server-proxy \
      && conda clean --all -f -y \
      && conda build purge-all

ENTRYPOINT ["tini", "-g", "--"]
