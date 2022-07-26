FROM segment/chamber:2.10.6 AS chamber
# FROM mcr.microsoft.com/azure-cli:2.9.1 AS azure-cli
FROM jshimko/kube-tools-aws:3.8.1 AS ci-cd-ready

COPY --from=chamber /chamber /usr/local/bin/chamber
# Install azure cli on alpine
RUN apk add --no-cache -q --virtual=build gcc=10.3.1_git20210424-r2 \ 
    musl-dev=1.2.2-r3 \
    python3-dev=3.9.5-r2 \
    libffi-dev=3.3-r2 \
    openssl-dev=1.1.1q-r0 \
    cargo=1.52.1-r1 \
    make=4.3-r0
RUN pip install --no-cache-dir pip==22.2
RUN pip install --no-cache-dir azure-cli==2.38.0
RUN apk del --purge build
