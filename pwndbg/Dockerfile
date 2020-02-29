# Dockerfile to install pwndbg
#
# docker build -t pwndbg:ubuntu19.10 .
# docker run --rm --volume $PWD:/pwd --cap-add=SYS_PTRACE \
#   --security-opt seccomp=unconfined -d --name pwndbg -i pwndbg:ubuntu19.10
# docker exec -it pwndbg /bin/bash

# Start from minimalctf
FROM minimalctf:ubuntu19.10

# install gdb and git
RUN apt-get install --assume-yes gdb git

# install pwndbg
RUN mkdir tools
RUN cd tools && \
git clone https://github.com/pwndbg/pwndbg && \
cd pwndbg && \\
./setup.sh

