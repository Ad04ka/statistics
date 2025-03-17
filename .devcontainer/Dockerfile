FROM mcr.microsoft.com/devcontainers/anaconda:3

# Install R, Jupyter Notebook, and R Kernel
RUN apt-get update && \
    apt-get install -y r-base r-base-dev libssl-dev libcurl4-openssl-dev libxml2-dev && \
    conda install -y jupyter && \
    R -e "install.packages(c('IRkernel', 'tidyverse', 'ggplot2', 'dplyr'), repos='http://cran.r-project.org')" && \
    R -e "IRkernel::installspec(user = FALSE)"

# Set environment
ENV R_HOME /usr/lib/R
ENV PATH=$R_HOME/bin:$PATH

# Set Jupyter as the default working directory
WORKDIR /workspace
