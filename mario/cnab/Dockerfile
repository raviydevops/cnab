FROM python:3.6.8-jessie

RUN apt-get update && apt-get install -y bash
RUN pip3 install awscli

RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && \
    chmod +x ./kubectl && \
    mv ./kubectl /usr/local/bin/kubectl

RUN curl -LO https://storage.googleapis.com/kubernetes-helm/helm-v2.14.0-linux-amd64.tar.gz && \
    tar -xzvf helm-v2.14.0-linux-amd64.tar.gz && \
    mv linux-amd64/helm /usr/local/bin/helm && \
    mv linux-amd64/tiller /usr/local/bin/tiller

RUN curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.12.7/2019-03-27/bin/linux/amd64/aws-iam-authenticator && \
    chmod +x ./aws-iam-authenticator && \
    mv aws-iam-authenticator /usr/local/bin/aws-iam-authenticator

COPY mario/cnab/Dockerfile /cnab/Dockerfile
COPY mario/cnab/app /cnab/app
COPY charts cnab/app/charts

ENTRYPOINT ["/cnab/app/run"]
