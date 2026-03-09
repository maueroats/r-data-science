# Use a Python base (since you might use Jupyter)
FROM mcr.microsoft.com/devcontainers/python:3.11

# Install R and system dependencies for common R packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends jupyter r-base r-cran-tidyverse r-cran-irkernel libxml2-dev libssl-dev libcurl4-openssl-dev

# Pre-install specific R packages
# This saves you from running install.packages() every time
RUN Rscript -e "install.packages(c('palmerpenguins'), repos='https://cran.rstudio.com/')"

# Register the R kernel so it shows up in Jupyter Notebooks
RUN Rscript -e "IRkernel::installspec(user = FALSE)"
