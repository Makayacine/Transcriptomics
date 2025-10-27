FROM python:3.11-slim

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y --no-install-recommends \
    openjdk-21-jdk-headless curl ca-certificates gcc g++ make tini \
 && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir \
    jupyterlab==4.* \
    pyspark==3.5.5 py4j==0.10.9.7 \
    pyfastx pandas matplotlib seaborn==0.13.2  scipy statsmodels

# Create non-root user
RUN useradd -ms /bin/bash app
USER app
WORKDIR /workspace
ENV HOME=/home/app PYSPARK_PYTHON=python SPARK_LOCAL_IP=127.0.0.1
EXPOSE 8889

CMD ["bash","-lc","jupyter lab --ip=0.0.0.0 --port=8889 --ServerApp.token='' --ServerApp.password='' --no-browser"]

# Disable Jupyter auth by default
USER root
RUN mkdir -p /home/app/.jupyter && \
    printf "c.ServerApp.token = ''\nc.ServerApp.password = ''\nc.IdentityProvider.token = ''\n" \
    > /home/app/.jupyter/jupyter_server_config.py && \
    chown -R app:app /home/app/.jupyter
USER app
