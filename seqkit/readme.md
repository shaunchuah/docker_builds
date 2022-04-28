# Docker Container for SeqKit

Original seqkit source here: <https://github.com/shenwei356/seqkit>

Docker container for seqkit using alpine linux as base image

Used to count CG sequences

SeqKit binary is in /data

SeqKit version used here to build docker image: v2.0.0

## Build notes

- Linux 64 bit binary copied into /data
- /data added to path
- Ubuntu base image - tried Alpine base but caused nextflow to fail on Azure execution
- SeqKit has native support for gzipped files

Build command from repo root

```sh
docker build -t shaunchuah/seqkit:<tag> .
```

## Usage

Running Docker locally in interactive fashion, note you should mount your directory into /data:

```sh
docker run -it --rm -v ${pwd}:/data shaunchuah/seqkit
```

Command for finding CG repeats:

```sh
seqkit locate --ignore-case --only-positive-strand --pattern "CG" <input file> | wc -l >> <output_file>
```

Full seqkit manual here: <https://bioinf.shenwei.me/seqkit/>

## Docker Image Location

```sh
shaunchuah/seqkit
```
