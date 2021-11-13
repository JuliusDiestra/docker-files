FROM ubuntu:18.04

RUN apt-get update && \
    apt-get install -y cmake \
            build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists

# Create working directory with applications
WORKDIR /tmp/app_dir

