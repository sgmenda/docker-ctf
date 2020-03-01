# A minimal dockerfile for ctfs
#
# Inspired by 
# https://github.com/LiveOverflow/pwn_docker_example/blob/master/ctf/Dockerfile
#
# Build image:
#   docker build -t minimalctf:ubuntu19.10 .
# Run image to create container:
#   docker run --rm --volume $PWD:/pwd --cap-add=SYS_PTRACE \
#       --security-opt seccomp=unconfined -d --name minimalctf \
#       -i minimalctf:ubuntu19.10
# Exec shell in container:
#   docker exec -it minimalctf /bin/bash

# Some comments:
# 1. --rm in the docker run cleans up the container after it exists (by default,
#    the file system of a container persists after exiting.)
# 2. --volume binds the current working directory to /pwd in the container.
# 3. --cap-add=SYS_PTRACE allows container processes to trace processes (gdb
#    needs this.)
# 4. -d runs it as a detached process

# Start from ubuntu 19.10
FROM ubuntu:19.10

# Use UTF-8
ENV LC_CTYPE C.UTF-8

RUN apt-get update

# Install basic stuff
RUN apt-get install --assume-yes build-essential strace ltrace curl wget gcc

RUN apt-get install --assume-yes vim gdb git

RUN apt-get install --assume-yes netcat

# Create user and set working dir to user's home directory
RUN useradd --create-home --shell /bin/bash haxor
WORKDIR /home/haxor

