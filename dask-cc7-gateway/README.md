This Dockerfile forces downgrade to a list of packages required by dask-gateway to function properly with out-of-the-box images for the dask-gateway-api server. We are aware that these versions are very outdated and will be maintaining them only in order to avoid incompatibility issues with the current deployment of dask-gateway at FNAL.

It is solely a forced conda downgrade on a number of package versions required by the current dask-gateway images published in DockerHub: https://hub.docker.com/r/daskgateway/dask-gateway-server/tags?page=1&ordering=last_updated

This will hopefully produce a functional image between the latest possible coffea-dask-cc-7 with the pinned packages in downgraded versions.
