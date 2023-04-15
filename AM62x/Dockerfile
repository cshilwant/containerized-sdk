ARG BASE_DISTRO=amd64/ubuntu:22.04

FROM $BASE_DISTRO

LABEL org.opencontainers.image.source https://github.com/cshilwant/containerized-sdk/AM62X
 
RUN export DEBIAN_FRONTEND=noninteractive; apt-get update
RUN export DEBIAN_FRONTEND=noninteractive; \
         apt-get install -y build-essential autoconf automake \
         bison flex libssl-dev bc u-boot-tools swig wget tar

RUN mkdir /work && cd /work && \
         wget https://www.dropbox.com/s/wuec2dwxj0gl7fb/processor-sdk-linux-bundle-am62xx-evm.tar.xz?dl=0 && \
         tar -xf processor-sdk-linux-bundle-am62xx-evm.tar.xz && \
         
ENTRYPOINT ["/bin/bash", "/work/"]
