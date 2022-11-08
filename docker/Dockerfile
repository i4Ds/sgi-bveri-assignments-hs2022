# BSc Informatik - bverI HS22
FROM jupyter/minimal-notebook:2022-09-12

LABEL maintainer="Marco Willi <marco.willi@fhnw.ch>"
LABEL description="BSc Informatik - bverI HS22 - Exercises"

USER root

RUN apt-get update && \
    apt-get install -y  \
        make && \
    apt-get clean

USER $NB_UID

RUN mamba install --quiet --yes \
    'line_profiler' \
    'memory_profiler' \
    'flask' \
    'pytest' \
    'altair' \
    'tabulate' \
    'plotly' \
    'seaborn' \
    'conda-forge::jupyter_contrib_nbextensions' \
    'conda-forge::mlxtend' \
    'conda-forge::texinfo' \
    'conda-forge::ipywidgets' \
    'conda-forge::xeus-python' \
    'pytorch::pytorch' \
    'pytorch::torchvision' \
    'pytorch::torchaudio' \
    'pytorch::torchmetrics' \
    'pytorch::cudatoolkit=11.3' \
    'pytorch-lightning' \
    'python-gitlab' \
    'timm' \
    'pyppeteer' && \
    mamba clean --all -f -y && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

RUN pip install nbgrader==0.8.0 \
    torchshow \
    torchviz
