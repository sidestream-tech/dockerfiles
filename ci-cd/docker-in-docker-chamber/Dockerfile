FROM segment/chamber:2.10.6 AS chamber

FROM docker:20.10.10

COPY --from=chamber /chamber /usr/local/bin/chamber
