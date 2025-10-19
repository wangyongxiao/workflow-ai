FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    curl \
    ninja-build \
    pkg-config \
    libssl-dev

RUN git clone --branch v0.11.11 --depth 1 https://github.com/sogou/workflow.git && \
    cd workflow && cmake -B cmake-build -G Ninja && cmake --build cmake-build && \
    cp -r ./_lib/* /usr/lib/ && cp -r ./_include/workflow /usr/include/ && \
    cd .. && rm -rf workflow
