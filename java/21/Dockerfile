FROM ghcr.io/diamonddrakeventures/yolks/os:alpine

LABEL org.opencontainers.image.authors="Diamond Drake Ventures"
LABEL org.opencontainers.image.source="https://github.com/diamonddrakeventures/yolks"
LABEL org.opencontainers.image.licenses="MIT"

USER root
ENV USER=root

RUN apk add --update --no-cache \
    openjdk21

USER container
ENV USER=container
