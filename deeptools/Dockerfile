FROM python:3.10-slim-buster

ARG DEEPTOOLS_VERSION="3.5"

RUN apt-get update && apt-get install --no-install-recommends -y \
    build-essential \
    zlib1g-dev \
    && apt-get autoclean && rm -rf /var/lib/apt/lists/*

RUN pip install deeptools==${DEEPTOOLS_VERSION}

WORKDIR /data

CMD ["bash"]