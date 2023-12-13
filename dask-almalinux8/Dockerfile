ARG PYTHON=3.8
FROM coffeateam/coffea-base-almalinux8:0.7.22-py${PYTHON}

# Dask + Distributed
# remember to check bokeh/dask compatibility next time we update dask
RUN mamba install --yes \
      -c conda-forge \
      conda-build \
      jemalloc \
      python-blosc \
      cytoolz \
      bokeh==2.4.3 \
      dask==2023.3.1 \
      distributed==2023.3.1 \
      dask-gateway \
      dask-jobqueue \
      nomkl \
      scipy \
      tini \
      jupyter-server-proxy \
      htcondor==9.2.0 \
      && mamba clean --all --yes \
      && pip install --no-cache-dir fsspec-xrootd

# Add mount point for Singularity/Apptainer
RUN mkdir -p /opt/conda

RUN curl -L https://github.com/opensciencegrid/osg-vo-config/archive/refs/heads/master.tar.gz | \
    tar -xz --strip-components=1 --directory=/etc/grid-security --wildcards */vomses */vomsdir && \
    mv /etc/grid-security/vomses /etc

ENTRYPOINT ["tini", "-g", "--"]
