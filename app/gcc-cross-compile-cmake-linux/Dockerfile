FROM debian:buster-slim

# Install common tools
RUN \
    apt-get update -y && \
    apt-get install -y  --no-install-recommends \
        apt-transport-https \
        software-properties-common \
        ca-certificates \
        curl \
        libcurl4 \
        wget \
        rsync

# Install complier tools
RUN \
    apt-get update -y && \
    apt-get install -y  --no-install-recommends \
        build-essential \
        gcc \
        g++ \
        python-dev \
        make \
        cmake

# Install c++ library dependency
ADD ./libs /dep
RUN /dep/date/install.sh
RUN rm -rf /dep

# Container setting
WORKDIR /repo
