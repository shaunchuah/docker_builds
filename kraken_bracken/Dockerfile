# CONTAINER 
# shaunchuah/kraken_bracken
#
# SPECIAL NOTES
# For kraken2 and bracken, usage is as per original manual.
# For KrakenTools, usage is similar to the manual except for the path.
# Use 'python /krakentools/<script_name> <arguments>' instead.

FROM python:3.10-buster

# Upgrade by changing version numbers here
ARG K2VER="2.1.2"
ARG BRACKEN_VERSION="2.6.2"
ARG KRAKENTOOLS_VERSION="1.2"

# install dependencies and cleanup apt garbage
RUN apt-get update && apt-get -y --no-install-recommends install \
    wget \
    ca-certificates \
    zlib1g-dev \
    make \
    g++ \
    rsync \
    build-essential \
    cpanminus && \
    rm -rf /var/lib/apt/lists/* && apt-get autoclean

# perl module required for kraken2-build
RUN cpanm Getopt::Std

# DL Kraken2, unpack, and install
RUN wget https://github.com/DerrickWood/kraken2/archive/v${K2VER}.tar.gz && \
    tar -xzf v${K2VER}.tar.gz && \
    rm -rf v${K2VER}.tar.gz && \
    cd kraken2-${K2VER} && \
    ./install_kraken2.sh . && \
    mkdir /data /kraken2-db

ENV PATH="$PATH:/kraken2-${K2VER}" \
    LC_ALL=C

# DL Bracken
WORKDIR /bracken

RUN wget https://github.com/jenniferlu717/Bracken/archive/v${BRACKEN_VERSION}.tar.gz && \
    tar -xzf v${BRACKEN_VERSION}.tar.gz && \
    rm -rf v${BRACKEN_VERSION}.tar.gz && \
    cd Bracken-${BRACKEN_VERSION} && \
    chmod +x ./install_bracken.sh && \
    ./install_bracken.sh

ENV PATH="/bracken/Bracken-${BRACKEN_VERSION}:${PATH}"



# Install krakentools
WORKDIR /krakentools
RUN wget https://github.com/jenniferlu717/KrakenTools/archive/v${KRAKENTOOLS_VERSION}.tar.gz && \
    tar -xzf v${KRAKENTOOLS_VERSION}.tar.gz && \
    rm -rf v${KRAKENTOOLS_VERSION}.tar.gz && \
    mv KrakenTools-${KRAKENTOOLS_VERSION}/* .

ENV PATH="/krakentools:${PATH}"

WORKDIR /data
CMD ["bash"]
