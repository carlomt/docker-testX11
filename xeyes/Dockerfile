FROM ubuntu:focal
LABEL maintainer="carlo.mancini-terracciano@uniroma1.it"

LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="carlomt/xeyes"
LABEL org.label-schema.description="xeyes Docker image"
LABEL org.label-schema.url="https://github.com/carlomt/docker-testX11/xeyes"
LABEL org.label-schema.docker.cmd="docker build -t carlomt/xeyes:latest --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') --no-cache=true ."

RUN apt-get update && \
    apt-get -yq --no-install-recommends install \
    x11-apps \
    && \
    apt-get -y autoremove && \
    apt-get -y clean && \    
    rm -rf /var/cache/apt/archives/* && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT  ["xeyes"]