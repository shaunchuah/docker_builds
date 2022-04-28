# Containerization Readme

## Docker Hub Container Name

shaunchuah/kraken_biom

## Building the container

```sh
docker build . -t <tag_name_here>
```

## To run kraken-biom interactively in docker:

```sh
docker run -it --rm -v ${pwd}:/data shaunchuah/kraken_biom
```

## Build notes

I've included some test data in `kraken2_test_data` for easy testing of docker images
