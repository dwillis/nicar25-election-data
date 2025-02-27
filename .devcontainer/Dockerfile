FROM rocker/rstudio:latest

# Install additional dependencies
RUN apt-get update && apt-get install -y \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    && rm -rf /var/lib/apt/lists/*

# Create a setup script
RUN echo '#!/bin/bash\n\
echo "Configuring RStudio Server..."\n\
adduser --disabled-password --gecos "" rstudio\n\
echo "rstudio:rstudio" | chpasswd\n\
' > /usr/local/bin/configure-rstudio.sh && chmod +x /usr/local/bin/configure-rstudio.sh

EXPOSE 8787
