FROM ubuntu:16.04

MAINTAINER r33c3 

COPY ./afl /mnt/afl

RUN apt-get update
RUN apt-get install -y sudo git software-properties-common make gcc g++ wget cmake
RUN wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
RUN apt-get update
RUN apt-get install -y clang-6.0 lldb-6.0 llvm-6.0

RUN ln -s /usr/bin/llvm-config-6.0 /usr/bin/llvm-config
RUN ln -s /usr/bin/clang-6.0 /usr/bin/clang
RUN ln -s /usr/bin/clang++-6.0 /usr/bin/clang++

RUN cd /mnt/afl && make
RUN cd /mnt/afl/llvm_mode && make
RUN cd /mnt/afl && make install

