# CONTAINER 
# shaunchuah/multiqc
#
# SPECIAL NOTES
# This container was built because ewels/multiqc doesn't work well
# with nextflow as the base alpine linux image doesn't have bash.

FROM python:3.9-slim-buster

RUN pip install multiqc==1.12

WORKDIR /data

CMD ["bash"]
