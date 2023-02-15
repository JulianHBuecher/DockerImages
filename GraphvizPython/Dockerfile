FROM docker.io/python:3.10-slim-bullseye AS BUILD

USER root

RUN apt-get -yq update && apt-get install -yqq \
    ssh python3-venv python3-pip graphviz

ARG UNAME=jenkins
ARG UID=1000
ARG GID=1000
ENV HOME /home/${UNAME}

RUN groupadd -g $GID -o $UNAME
RUN useradd -u $UID -g $GID --create-home --home-dir $HOME -s /bin/bash $UNAME \
    && mkdir -p $HOME \
    && chown -R $UNAME:$UNAME $HOME

WORKDIR $HOME
USER $UNAME

RUN mkdir -p /home/$UNAME/.ssh
RUN touch /home/$UNAME/.ssh/known_hosts

ENV PATH="${PATH}:${HOME}/.local/bin"
