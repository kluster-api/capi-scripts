FROM python:3.9.20-alpine3.20 AS builder

LABEL org.opencontainers.image.source=https://github.com/kluster-api/capi-deployer

ARG TARGETOS
ARG TARGETARCH

ARG INFRASTRUCTURE_VERSION="v1.17.0"
ARG CLUSTER_API_VERSION="v1.8.3"

RUN apk add --update --no-cache bash jq ca-certificates curl openssl unzip wget gcc musl-dev libffi-dev cargo make

RUN pip install azure-cli

COPY script.sh .

RUN chmod +x script.sh
RUN ./script.sh
