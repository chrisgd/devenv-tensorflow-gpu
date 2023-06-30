# use the gpu-enabled tensorflow 
FROM tensorflow/tensorflow:latest-gpu-jupyter

ENV LANG C.UTF-8
ENV SHELL /bin/bash

# define the user, we'll call them mler
ENV USERNAME=mler \
    USER_UID=2001 \
    USER_GID=2001 \
    DEBIAN_FRONTEND=noninteractive

# set up some packages
RUN apt-get update
RUN apt-get install -y \
    apt-utils \
    bash \
    build-essential \
    ca-certificates \
    curl \
    sudo \
    wget \
    xz-utils \
    z3 \
    zlib1g-dev

# set up user and group
RUN groupadd --gid $USER_GID $USERNAME && \
    useradd -ms /bin/bash -K MAIL_DIR=/dev/null --uid $USER_UID --gid $USER_GID -m $USERNAME && \
    echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME && \
    chmod 0440 /etc/sudoers.d/$USERNAME

USER ${USER_UID}:${USER_GID}
WORKDIR /home/${USERNAME}
ENV PATH="/home/${USERNAME}/.local/bin:/home/${USERNAME}/.cabal/bin:/home/${USERNAME}/.ghcup/bin:$PATH"

RUN echo "export PATH=$PATH" >> /home/$USERNAME/.profile
