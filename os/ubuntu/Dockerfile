FROM ubuntu:latest

LABEL org.opencontainers.image.authors="Diamond Drake Ventures"
LABEL org.opencontainers.image.source="https://github.com/diamonddrakeventures/yolks"
LABEL org.opencontainers.image.licenses="MIT"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
        iproute2 \
        tini \
        wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
RUN useradd -m -d /home/container container

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

STOPSIGNAL SIGINT

COPY --chown=container:container ./entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT [ "/usr/bin/tini", "-g", "--" ]
CMD [ "/entrypoint.sh" ]
