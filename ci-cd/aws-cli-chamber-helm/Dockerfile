FROM segment/chamber:2.10.6 AS chamber

FROM jshimko/kube-tools-aws:3.8.1 AS ci-cd-ready

COPY --from=chamber /chamber /usr/local/bin/chamber
