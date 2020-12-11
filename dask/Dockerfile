FROM coffeateam/coffea-base:latest

# Dask + Distributed
RUN conda install --yes --freeze-installed \
      -c conda-forge \
      conda-build \
      python-blosc \
      cytoolz \
      bokeh==2.2.3 \
      dask==2.30.0 \
      distributed==2.30.0 \
      lz4 \
      nomkl \
      numpy==1.19.2 \
      pandas==1.1.4 \
      numba==0.51.2 \
      scipy==1.5.3 \
      matplotlib==3.3.2 \
      tini==0.18.0 \
      jupyter-server-proxy \
      && conda clean --all -f -y \
      && conda build purge-all


ENTRYPOINT ["tini", "-g", "--"]
