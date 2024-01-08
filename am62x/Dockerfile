ARG BASE_DISTRO=amd64/ubuntu:22.04
FROM $BASE_DISTRO
LABEL org.opencontainers.image.source https://github.com/cshilwant/containerized-sdk/AM62X
RUN export DEBIAN_FRONTEND=noninteractive; apt-get update
RUN export DEBIAN_FRONTEND=noninteractive; \
         apt-get install -y build-essential autoconf automake bison flex libssl-dev bc u-boot-tools swig python3 python3-pip wget vim nano
RUN export DEBIAN_FRONTEND=noninteractive; \
         pip3 install -y jsonschema pyelftools
RUN mkdir /tmp/work && cd /tmp/work && \
         wget https://dr-download.ti.com/software-development/software-development-kit-sdk/MD-PvdSyIiioq/09.01.00.08/ti-processor-sdk-linux-am62xx-evm-09.01.00.08-Linux-x86-Install.bin && \
         chmod +x ./ti-processor-sdk-linux-am62xx-evm-09.01.00.08-Linux-x86-Install.bin && \
         ./ti-processor-sdk-linux-am62xx-evm-09.01.00.08-Linux-x86-Install.bin
WORKDIR /tmp/work
ENTRYPOINT ["/bin/bash"]
