ARG BASE_DISTRO=amd64/ubuntu:22.04
FROM $BASE_DISTRO
LABEL org.opencontainers.image.source https://github.com/cshilwant/containerized-sdk/AM62X
RUN export DEBIAN_FRONTEND=noninteractive; apt-get update
RUN export DEBIAN_FRONTEND=noninteractive; \
         apt-get install -y apt-utils build-essential autoconf automake \
         bison flex libssl-dev bc u-boot-tools swig wget tar vim nano
RUN mkdir /tmp/work && cd /tmp/work && \
         wget https://software-dl.ti.com/processor-sdk-linux/esd/AM62X/08_06_00_42/processor-sdk-linux-bundle-am62xx-evm.tar.xz && \
         tar -xf processor-sdk-linux-bundle-am62xx-evm.tar.xz && rm processor-sdk-linux-bundle-am62xx-evm.tar.xz
WORKDIR /tmp/work
ENTRYPOINT ["/bin/bash"]
