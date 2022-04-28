# Bioinformatics Docker Builds

A collection of Dockerfiles used to build reusable containers for use with nextflow. Huge thanks and credits to the original authors listed here.

<https://hub.docker.com/u/shaunchuah>

## shaunchuah/kraken_bracken

Base image: python3.10-buster (debian-based)

- [kraken2 v2.1.2](https://github.com/DerrickWood/kraken2)
- [bracken v2.6.2](https://github.com/jenniferlu717/Bracken)
- [krakentools v1.2](https://github.com/jenniferlu717/KrakenTools)

## shaunchuah/krakentools

Lightweight version of above container if you only need to quickly use a few scripts.

- [krakentools v1.2](https://github.com/jenniferlu717/KrakenTools)

## shaunchuah/kraken-biom

- [kraken-biom v1.0.1](https://github.com/smdabdoub/kraken-biom)

## shaunchuah/multiqc

Original container from ewels doesn't play well with nextflow as it is alpine linux based.

- [multiqc v1.12](https://github.com/ewels/MultiQC)

## shaunchuah/seqkit

- [seqkit v2.0.0](https://github.com/shenwei356/seqkit)

## shaunchuah/cpgiscan

- [cpgiscan commit 13948ad 16/02/2015](https://github.com/jzuoyi/cpgiscan)
