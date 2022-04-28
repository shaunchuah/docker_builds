# CONTAINER 
# shaunchuah/krakentools
#
# Basic python container to run krakentools if simple conversions are needed.
# SPECIAL NOTES:
# For KrakenTools, usage is similar to the manual except for the path.
# Use 'python /krakentools/<script_name>.py <arguments>' instead.

FROM python:3.10-slim-buster

WORKDIR /krakentools

COPY /KrakenTools .

ENV PATH="/krakentools:${PATH}"

WORKDIR /data

CMD ["bash"]
