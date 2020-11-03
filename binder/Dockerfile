FROM pangeo/pangeo-notebook:master

ENV DASK_DISTRIBUTED__DASHBOARD_LINK='/user/{JUPYTERHUB_USER}/proxy/{port}/status'
ENV DASK_LABEXTENSION__FACTORY__MODULE='dask_gateway'
ENV DASK_LABEXTENSION__FACTORY__CLASS='GatewayCluster'
