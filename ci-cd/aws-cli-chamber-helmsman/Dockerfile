FROM segment/chamber:2.10.6 AS chamber
FROM jshimko/kube-tools-aws:3.8.1 AS ci-cd-ready
COPY --from=chamber /chamber /usr/local/bin/chamber
# * Helm diff # https://github.com/databus23/helm-diff
RUN helm plugin install https://github.com/databus23/helm-diff
# * helmsman # https://github.com/Praqma/helmsman#install
RUN curl -L https://github.com/Praqma/helmsman/releases/download/v3.11.0/helmsman_3.11.0_linux_amd64.tar.gz | tar zx
RUN mv helmsman /usr/local/bin/helmsman
CMD "/bin/bash"
