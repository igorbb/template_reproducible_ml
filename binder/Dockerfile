FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu18.04

# Build Args
ARG NB_UID=1000
ARG NB_USER=user

# ENV is necessary when attaching a nvidia. It can be left here if there is no nvidia runtime as well.
ENV NVIDIA_VISIBLE_DEVICES=all NVIDIA_DRIVER_CAPABILITIES=compute,utility
ENV PATH=/oneoff/conda/bin:$PATH HOME=/oneoff
ENV HOME /home/${NB_USER}
ENV USER ${NB_USER}

# Install Libraries
RUN apt-get update && \
    #install pakaches
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    apt-transport-https \
    apt-utils \
    build-essential \
    curl \
    graphviz \
    g++\
    locales \
    moreutils \
    tzdata \
    wget  \
    && locale-gen en_US.UTF-8 && ldconfig && \
    # create sources.list so we can add debian repos
    mkdir -p /etc/apt/sources.list.d  && \
    # add conda
    curl https://repo.anaconda.com/pkgs/misc/gpgkeys/anaconda.asc | apt-key add - && \
    echo "deb [arch=amd64] https://repo.anaconda.com/pkgs/misc/debrepo/conda stable main" > /etc/apt/sources.list.d/conda.list && \
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends conda && \
    adduser --disabled-password --gecos "Default user" --uid ${NB_UID} ${NB_USER} && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ${HOME}/.bashrc && \
    # setup chown for user
    chown ${USERID}:${USERID} -R /tmp/ && \
    # Clean
    apt-get clean  && \
    apt-get autoremove  && \
    rm -rf /var/lib/apt/lists/* /tmp/* ~/* /var/cache/debconf

WORKDIR ${HOME}
USER ${NB_USER}
# Install environment.yml on conda
COPY binder/environment.yml ${HOME}/environment.yml
COPY code ${HOME}/code
COPY checklist ${HOME}/checklist
RUN /opt/conda/bin/conda env create -f ${HOME}/environment.yml && \
    echo "/opt/conda/bin/conda activate $(head -1 ${HOME}/environment.yml | cut -d' ' -f2)" >> ${HOME}/.bashrc
ENV PATH ${HOME}/.conda/envs/template/bin:$PATH
