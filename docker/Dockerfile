FROM mambaorg/micromamba:git-7545124-jammy as sandbox-conda

USER root
COPY environment.yml /conf/
RUN micromamba create  -y -p /env -f /conf/environment.yml && \
    micromamba clean --all --yes && \
    micromamba env export -p /env --explicit

ARG MAMBA_DOCKERFILE_ACTIVATE=1

FROM ubuntu:jammy-20220815

RUN apt-get update && apt-get install -y git vim

ARG user=jovyan
ARG uid=1000
ARG gid=100

RUN useradd -l -m -s /bin/bash -N -g $gid -u $uid $user

COPY --chown=$uid:$gid --from=sandbox-conda /env /env

ENV LC_ALL=C.UTF-8 \
    SHELL=bash \
    GDAL_DRIVER_PATH=/env/lib/gdalplugins \
    PROJ_LIB=/env/share/proj \
    GDAL_DATA=/env/share/gdal \
    PATH=/env/bin:$PATH

USER $user

WORKDIR "/home/$user"

EXPOSE 8787 8888
ENTRYPOINT ["tail", "-f", "/dev/null"]

