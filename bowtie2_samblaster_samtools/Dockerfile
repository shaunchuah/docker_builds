FROM python:3.10-slim-buster

RUN apt-get update && apt-get install --no-install-recommends -y \
 libncurses5-dev \
 libbz2-dev \
 liblzma-dev \
 libcurl4-gnutls-dev \
 zlib1g-dev \
 libssl-dev \
 gcc \
 perl \
 bzip2 \
 gnuplot \
 ca-certificates \
 wget \
 make \
 g++ \
 unzip \
 gawk && \
 apt-get autoclean && rm -rf /var/lib/apt/lists/*

ARG SAMTOOLSVER=1.15.1

WORKDIR /bowtie2
COPY . .
RUN unzip bowtie2-2.4.5-linux-x86_64.zip && \
    rm bowtie2-2.4.5-linux-x86_64.zip && \
    mv bowtie2-2.4.5-linux-x86_64/* /usr/local/bin

WORKDIR /samblaster
RUN wget https://github.com/GregoryFaust/samblaster/releases/download/v.0.1.26/samblaster-v.0.1.26.tar.gz && \
    tar -xzf samblaster-v.0.1.26.tar.gz && \
    rm samblaster-v.0.1.26.tar.gz && \
    cd samblaster-v.0.1.26 && \
    make

RUN cp samblaster-v.0.1.26/samblaster /usr/local/bin

WORKDIR /samtools
RUN wget https://github.com/samtools/samtools/releases/download/${SAMTOOLSVER}/samtools-${SAMTOOLSVER}.tar.bz2 && \
 tar -xjf samtools-${SAMTOOLSVER}.tar.bz2 && \
 rm samtools-${SAMTOOLSVER}.tar.bz2 && \
 cd samtools-${SAMTOOLSVER} && \
 ./configure && \
 make && \
 make install
ENV PATH="/samtools:${PATH}"

WORKDIR /data

CMD ["bash"]
