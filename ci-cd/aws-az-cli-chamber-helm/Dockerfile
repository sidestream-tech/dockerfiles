FROM segment/chamber:2.10.6 AS chamber
# FROM mcr.microsoft.com/azure-cli:2.9.1 AS azure-cli
FROM jshimko/kube-tools-aws:3.8.1 AS ci-cd-ready

COPY --from=chamber /chamber /usr/local/bin/chamber
# Install azure cli on alpine
RUN apk add py3-pip
RUN apk add gcc musl-dev python3-dev libffi-dev openssl-dev cargo make
RUN pip install --upgrade pip
RUN pip install azure-cli
