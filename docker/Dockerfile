FROM debian:stable-slim

ENV TF_SWITCH_DIR=/opt/tfswitch \
    AWS_CLI_DIR=/opt/aws-cli \
    CONDA_DIR=/opt/conda

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y \
    curl \
    unzip \
    git

# TFSwitch
ENV TF_PRODUCT=terraform
RUN curl -L https://raw.githubusercontent.com/warrensbox/terraform-switcher/master/install.sh | bash -s -- -b $TF_SWITCH_DIR/bin
ENV PATH=$TF_SWITCH_DIR/bin:$PATH
RUN tfswitch --latest

# Conda
RUN curl "https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-$(uname -m).sh" -o /tmp/miniconda.sh && \
    /bin/bash /tmp/miniconda.sh -b -p $CONDA_DIR
ENV PATH=$CONDA_DIR/bin:$PATH
RUN conda create -n py3 python=3 -y && conda init

# AWS CLI
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-$(uname -m).zip" -o "/tmp/awscliv2.zip"
RUN unzip /tmp/awscliv2.zip -d /tmp
RUN /bin/bash /tmp/aws/install --bin-dir $AWS_CLI_DIR/bin --install-dir $AWS_CLI_DIR/aws-cli --update
ENV PATH=$AWS_CLI_DIR/bin:$PATH

RUN rm -rf /tmp/*

CMD ["bash"]