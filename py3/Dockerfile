FROM python:3.11-slim-bullseye


RUN apt update && apt -y upgrade
RUN apt install -y \
    tzdata \
    vim \
&& ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
&& apt clean \
&& rm -rf /var/lib/apt/lists/*

ENV TZ=Asia/Tokyo


## Jupyterlab install
RUN python3 -m pip install --upgrade pip \
&& pip install --no-cache-dir \
    black \
    jupyterlab \
    jupyterlab_code_formatter \
    jupyterlab-git \
    lckr-jupyterlab-variableinspector \
    jupyterlab_widgets \
    ipywidgets \
    import-ipynb


## main package
RUN pip install --no-cache-dir \
    matplotlib \
    numpy \
    pandas \
    requests
