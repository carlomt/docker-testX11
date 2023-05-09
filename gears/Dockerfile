FROM ubuntu:focal
LABEL maintainer="carlo.mancini-terracciano@uniroma1.it"

LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="carlomt/gears"
LABEL org.label-schema.description="glxgears Docker image"
LABEL org.label-schema.url="https://github.com/carlomt/docker-testX11/gears"
LABEL org.label-schema.docker.cmd="docker build -t carlomt/gears:latest --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') --no-cache=true ."

ENV LIBGL_ALWAYS_INDIRECT=1

RUN apt-get update && \
    apt-get -yq --no-install-recommends install \
    mesa-utils \
    libgl1-mesa-glx \
    && \
    apt-get -y autoremove && \
    apt-get -y clean && \    
    rm -rf /var/cache/apt/archives/* && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT  ["glxgears"]