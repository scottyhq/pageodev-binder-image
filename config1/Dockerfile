# syntax = docker/dockerfile:1.4
FROM mambaorg/micromamba:0.23.1 as solver

RUN --mount=type=bind,source=env.yaml,target=/tmp/env.yaml \
    micromamba install -y -f /tmp/env.yaml \
    && micromamba clean --all --yes 
eot


FROM condaforge/mambaforge:4.12.0-0

# Cache-mount from previous build stage
# NOTE: subsequent 'build' commands will keep adding to this cache locally, but not stored in image!
RUN --mount=type=cache,from=solver,source=/opt/conda/pkgs,target=/opt/conda/pkgs \
    mamba create -y -n notebook python=3.9 pystac
