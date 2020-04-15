FROM pytorch/pytorch:1.0.1-cuda10.0-cudnn7-runtime

ARG PYTHON_VERSION=3.6
ENV GIT_SSL_NO_VERIFY=1

# apt install
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
         curl \
         git \
         vim \
         groff-base # awscli

# pip install
COPY requirements.txt /tmp/
RUN pip install --upgrade pip && \
    pip install -r /tmp/requirements.txt

# install gcloud
RUN echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list && \
   apt-get install -y apt-transport-https ca-certificates && \
   curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key --keyring /usr/share/keyrings/cloud.google.gpg add - && \
   apt-get update && apt-get install -y google-cloud-sdk

# make dir
RUN mkdir -p /opt/config \
             /opt/data/raw \
             /opt/data/interim \
             /opt/data/processed \
             /opt/data/external \
             /opt/features \
             /opt/logs \
             /opt/models \
             /opt/notebook \
             /opt/scripts \
             /opt/utils

# cd
WORKDIR /opt

# expose port TensorBoard
EXPOSE 6006
# expose port TensorBoard
EXPOSE 8888
