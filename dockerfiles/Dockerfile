FROM ghcr.io/taffish-org/debian:12

LABEL maintainer="taffish@163.com"

WORKDIR /root

COPY . .

RUN apt-get update

RUN apt-get install -y curl git gcc g++ make 

RUN apt-get install -y zlib1g-dev

RUN git clone --recursive https://github.com/ShiLab-Bioinformatics/subread && \
    cd subread/src && make -f Makefile.Linux && \
    mv ../bin/utilities/* ../bin/ && \
    rmdir ../bin/utilities && \
    cp ../bin/* /usr/local/bin/ && \
    rm -rf /var/lib/apt/lists/*

ENV TAFFISH_ENV=TAFFISH
ENV TAFFISH_NAME=subread
