FROM continuumio/miniconda

LABEL name="QMKJB000_bcell_ranalysis"
LABEL authors="Gisela Gabernet and Laurence Kuhlburger"
LABEL organization="Quantitative Biology Center"
LABEL description="Downstream analysis of BCR transcriptome isolated from PBMCs"
LABEL maintainer="Gisela Gabernet and Laurence Kuhlburger <laurence.kuhlburger@uni-tuebingen.de>"  
LABEL version="0.1.0"
LABEL github="https://github.com/qbicsoftware"

# Install procps so that Nextflow can poll CPU usage
RUN apt-get update && apt-get install -y procps && apt-get clean -y 
# Update the base version of conda
RUN conda update -n base conda
# Copy the list of R packages into the container's /tmp dir
COPY environment.yml /tmp
RUN conda update -n base conda && \
    conda env create -f /tmp/environment.yml && \
    conda clean -a

ENV PATH /opt/conda/envs/QMKJB-ranalysis-0.1.0/bin:$PATH
